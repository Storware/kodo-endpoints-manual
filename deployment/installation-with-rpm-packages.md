---
description: The RPM packages are suitable for installation on Red Hat and CentOS.
---

# Installation with RPMs

## Prerequisites

1. Install CentOS/RHEL 8 minimal:
   * we recommend having Red Hat's support available if you're going to use RHEL
   * you can use version CentOS/RHEL 7 as well 
2. Make sure your OS is up to date \(as the `root` user\):

   ```text
   # dnf -y update
   ```

   If the kernel is updated, then you need to reboot your operating system.

3. Install kodo-endpoints  repository:

   * create a file `/etc/yum.repos.d/kodo-endpoints.repo` 
   * edit the file and insert the information presented below

   ```text
   [kodo-endpoints]
   name=Kodo for Endpoints
   baseurl=http://repo.storware.eu/kodo-endpoints/current
   enabled=1
   gpgcheck=0
   ```

4. Install MariaDB repository:

   * generate `.repo` file at [MariaDB download](https://downloads.mariadb.org/mariadb/repositories) site
   * copy and paste generated repo file into `/etc/yum.repos.d/MariaDB.repo`, so it looks similar to this \(this one for CentOS/RHEL 8\):

   ```
   # MariaDB 10.4 CentOS repository list - created 2021-08-08 11:18 UTC
   # http://downloads.mariadb.org/mariadb/repositories/
   [mariadb]
   name = MariaDB
   baseurl = http://yum.mariadb.org/10.4/centos8-amd64
   module_hotfixes=1
   gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
   gpgcheck=1
   ```

{% hint style="warning" %}
The only supported MariaDB database versions are 10.3 and 10.4. Do not generate `.repo` file for version 10.5.
{% endhint %}

## KODO for Endpoints server installation

KODO for Endpoints server consists of a server \(central management point with WebUI and MariaDB database\). To install the server components, do the following steps:

1. Log in as the `root` user.
2. Use the command below to install`kodo-for-endpoints`package.

```text
# yum install kodo-for-endpoints        
```

The installation process starts. Select "**y**" when asking about the GPG key:

```text
Retrieving key from 
https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
 Importing GPG key 0x1BB943DB: Userid : "MariaDB Package Signing Key 
package-signing-key@mariadb.org
" Fingerprint: 1993 69e5 404b d5fc 7d2f e43b cbcb 082a 1bb9 43db From : 
https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
 Is this ok [y/N]
```

The installation process should take a few minutes. 

The installation should be finished with the "**Complete**!" message.

## KODO server initialization

Once the KODO for Endpoints server is installed, you have to perform the server initialization. Before you start, make sure the MariaDB database service is running.

```text
# systemctl status mariadb
● mariadb.service - MariaDB 10.4.20 database server
   Loaded: loaded (/usr/lib/systemd/system/mariadb.service; enabled; vendor preset: disabled)
  Drop-In: /etc/systemd/system/mariadb.service.d
           └─migrated-from-my.cnf-settings.conf
   Active: active (running) since Thu 2021-08-05 09:27:56 CEST; 1 day 7h ago
```

If the service is not running, start it by executing the following command:

```text
# systemctl start mariadb
```

 As the `root` user run the following script:

```text
# /opt/storware/kodo-server/api-core/bin/kodo-init.sh --dbpassword xyz
```

Follow the instructions to complete the configuration.

{% hint style="info" %}
You can use the following parameters with the script:

**--dbpassword password -** password for kodo for endpoints database \(default: random value\)

**--dbport port -**database port number \(default: 3306\)

**--dbusername username -**database username \(default: kodo\)
{% endhint %}

#### Example:

```text
[root@localhost ~]# /opt/storware/kodo-server/api-core/bin/kodo-init.sh --dbrootpassword xxxxx
Storware KODO for Endpoints server initial configuration script (v1.0)
MariaDB host:  localhost
MariaDB port:  3306
MariaDB KODO database user:  kodo
MariaDB KODO user password:  HbhJhrhCfyrpak5nOWgWicEPRs3DgU52
MariaDB root password:  1qazxsw23edc
Creating symlinks
Connecting to database localhost:3306
Checking if database user exists
Checking if database exists
Creating db user
Creating database
Granting privilages
Configuring database
Restarting database
Updateing KODO for Endpoints configuration
Preparing dsmcert database
Start KODO server with: systemctl start kodo-for-endpoints
[root@localhost ~]#
```

The KODO server initialization script creates the **kodo-for-endpoints** service, which is the main server process. To start the **kodo-for-endpoints** service, execute the :

```text
# systemctl start kodo-for-endpoints
```

## Configuring firewall

1. You have to open the 8181 port \(for HTTPS, HTTP requires port 8080\) on the firewall. Here is an example:

   ```text
   # firewall-cmd --add-port=8181/tcp --permanent
   # firewall-cmd --complete-reload
   To check open ports:
   # firewall-cmd --list-all
   ```

2. Now you should be able to log into the web console using the URL: `https://KODO_HOST:8181`, where `KODO_HOST` is hostname or IP of your KODO for Endpoints server \(see the [Administration levels](administration-levels-1.md) section for credential info\)

Go to the [IBM Spectrum Protect server configuration](spectrum-protect-tsm-configuration.md) section to learn how to prepare and configure the IBM Spectrum Protect server for use with the KODO server.

