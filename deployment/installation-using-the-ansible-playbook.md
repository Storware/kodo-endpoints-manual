# Installation using the Ansible playbook

Before starting the installation process you need to prepare your server platform accordingly to the size of the organization you are going to protect \(see the [Sizing guide](../planning/sizing-guide/README.md) guide chapter\).

You can install a complete Kodo for Endpoints solution using the following 3 roles, available on the Ansible Galaxy:

* Kodo for Endpoints Server: [https://galaxy.ansible.com/xe0nic/ansible\_kodo\_endpoints_server](https://galaxy.ansible.com/xe0nic/ansible_kodo_endpoints_server)​
* IBM Spectrum Protect Server for Kodo: [https://galaxy.ansible.com/xe0nic/ansible_isp_server](https://galaxy.ansible.com/xe0nic/ansible_isp_server)​
* IBM Spectrum Protect Client for Kodo: [https://galaxy.ansible.com/xe0nic/ansible\_isp\_client](https://galaxy.ansible.com/xe0nic/ansible_isp_client)​

IBM Spectrum Protect Client role is defined as a dependency by both Kodo for Endpoints and ISP server. It means that it will be automatically installed and executed before the other 2 and the following scenarios are possible:

* all 3 are installed together (like in all-on-one installation script)
* host1 with ISP client + ISP server and host2 with ISP client + Kodo for Endpoints server

**Note:** 

* You don't need to install ISP server if you want to use your existing ISP installation - but remember to follow [IBM Spectrum Protect server configuration](deployment/spectrum-protect-tsm-configuration.md) section to prepare it for Kodo.

## Prerequisites <a id="prerequisites"></a>

You need to prepare CentOS/RHEL 8 server minimal for Kodo for Endpoints \(both roles can be installed on the same or different hosts\).

This example assumes that you have `root` access to this host and you have configured your Ansible to connect with SSH public-keys to your host. For example:

generate a key:

```text
# ssh-keygen -f ~/.ssh/id_rsa -P ""
```

and copy it to your CentOS/RHEL box:

```text
# ssh-copy-id -i ~/.ssh/id_rsa.pub root@YOUR_HOST
```

Host requirements (physical or virtual):

* system neeeds 16 GB of RAM and 4 vCPUs (this method will deploy small environment only) - please refer to the [Sizing guide](../../planning/sizing-guide/README.md) for more information
* solution needs at least 6 drives to be available (these needs to be attached to the host in the following order, as it determines their role)

  1. operating system and Kodo Server (100 GB)
  1. ISP database (100 GB)
  1. ISP active log (35 GB)
  1. ISP archive log (100 GB)
  1. database backups (100 GB)
  1. backup data (1 TB+ - more than 1 drive are supported with Ansible-based installation or when you provide YAML file with overridden parameters)
* the above-mentioned requirements are ready for all-in-one setup - if you want to split Kodo and ISP:
  * assume above-mentioned requirments for ISP component
  * additionally Kodo itself can easily use single 100 GB drive / 4 GB of memory and 2 vCPU.

* CentOS or RHEL 8 (optionally you can use version 7) minimal - make sure to have
   * RHEL 8 requires an active subscription
	* Internet connectivity - these are required for package installaltion
	* FQDN and hostname configured in the OS - which is also resolvable in your DNS


## Installation <a id="installation"></a>

This example assumes that you want to install both Kodo for Endpoints server and agent **using a single playbook** and **on the same host** \(single agent\) and currently this is the only supported deployment.

Run these on the system from which you run Ansible playbooks:

* Install Ansible roles:

```text
ansible-galaxy install xe0nic.ansible_isp_server
ansible-galaxy install xe0nic.ansible_kodo_endpoints_server
```

* Create a playbook directory and change its working directory, i.e: `mkdir kodo && cd kodo`
* Create an inventory file - i.e. `hosts`:

```text
[all:vars]
ansible_user = root

[server]
test.local
```

* Create a playbook file - `site.yml`:

```text
---

- hosts: server
  roles:
    - ansible-isp-server
    - ansible-kodo-endpoints-server
```

* You also **really** may want to override some parameters using `vars.yml` file:

```text
---
isp_server_download_url: "file:///tmp/8.1.12.000-IBM-SPSRV-Linuxx86_64.bin"
isp_client_download_url: "file:///tmp/8.1.12.0-TIV-TSMBAC-LinuxX86.tar"
isp_db_activelogsize: 16384
isp_fqdn: "test.local"
server_fqdn: "test.local"
```

   * Example:
     * overrides URLs to download ISP packages - to use locally downloaded files instead of official FTP (download from FTP may be quite slow, so you may want download them manually, upload them on the target host, and refer to the paths as in the example above)
     * specifies active log size to be 16 GB (defautlt is 32 GB - if the drive you provided is smaller than this value, you can reduce it with this parameter)
     * initializes 3 backup storage disks mounted in `/isp` subdirectories (recommended)

 Please refer to the roles' README filles for more invormation about available variables
 
* Run playbook: `ansible-playbook -i hosts site.yml`
  * Or if you override variables: `ansible-playbook -i hosts site.yml --extra-vars '@vars.yml'`
* After installation you should be able to log into your Kodo for Endpoints server: `https://kodo_endpoints_server_address` and your ISP status should be visible in the Kodo UI -> Settings -> IBM Spectrum Protect tab as **Connected**.

Once the installation completes - you can begin system configuration following information from the [Initial configuration](../deployment/initial-configuration.md)

## Variables <a id="variables"></a>

These two roles provide a lot of variables, mostly related to the ISP installation. 

It is very important to configure hostname on both ISP and Kodo hosts, so that roles will automatically use appropriate values. If you don't have them configured, you also can use `isp_fqdn` and `server_fqdn` variables to override them. 

If not defined, server play sets variable `isp_fqdn` and `server_fqdn` to the hostname reported by the OS on which it is installed. These will be used later to access APIs during Kodo installation and configure ISP connection.

By default KODO for Endpoints uses MariaDB 10.4 for CentOS - you can control the source, distribution, and version of your MariaDB with the following variables \(with their respective default values\):

```text
mariadb_version: "10.4"mariadb_distro: "centos8-amd64"mariadb_repo_url: "http://yum.mariadb.org/{{ mariadb_version }}/{{ mariadb_distro }}"mariadb_repo_gpg_key: "https://yum.mariadb.org/RPM-GPG-KEY-MariaDB"
```

IBM Spectrum Protect Server role requires to take care of storage and filesystem configuration a bit more carefully. Take a look speficically at the following variables:

```
isp_data_dir: "/isp"
isp_instance_path: "{{ isp_data_dir }}/{{ isp_instance_name }}"
isp_db_disk: "/dev/sdb"
isp_db_path: "{{ isp_data_dir }}/db"
isp_activelog_disk: "/dev/sdc"
isp_activelog_path: "{{ isp_data_dir }}/activelog"
isp_archlog_disk: "/dev/sdd"
isp_archlog_path: "{{ isp_data_dir }}/archlog"
isp_dbbackup_disk: "/dev/sde"
isp_dbbackup_path: "{{ isp_data_dir }}/dbbackup"
isp_storage_disks:
  - "/dev/sdf"
  ... // here you can add more disks
isp_storage_paths:
  - "{{ isp_data_dir }}/storage1"
  ... // here you add mountpoints for additional isp_storage_disks
```

Depending on the size of the disks you use - please adjust also DB backup max capacity size and active log size:

```text
isp_dbbackup_maxcap: "50G" //this one is a string used in ISP configuration (must be less than DB backup disk)
isp_db_activelogsize: 32768 //this one is in MB (must be less than disk used for active log)
```

Last but not least - downloading ISP packages from FTP may be slow. If you want to use your source or change the URL used for installation - you override `isp_server_download_url` and `isp_client_download_url` variables.

If you uploaded files to the hosts where the ISP components are installed

```text
isp_server_download_url: "file:///tmp/8.1.12.000-IBM-SPSRV-Linuxx86_64.bin"
isp_client_download_url: "file:///tmp/8.1.12.0-TIV-TSMBAC-LinuxX86.tar"
```

or use alternative URL - i.e.:
```text
isp_server_download_url: "https://alternative-url/8.1.12.000-IBM-SPSRV-Linuxx86_64.bin"
isp_client_download_url: "https://alternative-url/8.1.12.0-TIV-TSMBAC-LinuxX86.tar"
```
