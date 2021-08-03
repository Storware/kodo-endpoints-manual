---
description: The RPM packages are suitable for installation on Red Hat and CentOS.
---

# Installation with RPMs

## Prerequisites

1. Install CentOS/RHEL 8 minimal:
   * we recommend having Red Hat's support available if you're going to use RHEL
   * you also can use version CentOS/RHEL 7
2. Make sure your OS is up to date \(as the `root` user\):

   ```text
   #dnf -y update
   ```

   If the kernel is updated, then you need to reboot your operating system.

3. Install KODO-endpoints  repository:

   * create file `/etc/yum.repos.d/kodo-endpoints.repo`:

   ```text
   [kodo-endpoints]
   name=Kodo for Endpoints
   baseurl=https://repo.storware.eu/kodo-endpoints/current
   enabled=1
   gpgcheck=0
   ```

4. Install MariaDB repository:
   * generate .repo file at [MariaDB download](https://downloads.mariadb.org/mariadb/repositories) site
   * copy and paste generated repo file into `/etc/yum.repos.d/MariaDB.repo`, so it looks similar to this \(this one for CentOS/RHEL 8\):

```text
# MariaDB 10.5 CentOS repository list - created 2021-07-01 13:34 UTC
# http://downloads.mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.5/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

## KODO for Endpoints server installation

KODO for Endpoints server consists of a server \(central management point with WebUI and MySQL database\). To install the server do the following steps:

1. Log in as the `root` user.
2. Use the command below to install`kodo-for-endpoints`package.

```text
# yum install kodo-for-endpoints        
```

The installation process starts. Select "y" when asking about the GPG key:

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

## Configuring firewall

1. You may need to open the 8181 port \(for HTTPS, HTTP requires port 8080\) on your firewall. Here is an example:

   ```text
   firewall-cmd --add-port=8181/tcp --permanent
   firewall-cmd --complete-reload
   # To check open ports:
   firewall-cmd --list-all
   ```

2. Now you should be able to log into the web console using URL: `https://KODO_HOST:8181`, where `KODO_HOST` is hostname or IP of your KODO for Endpoints server

## KODO server initialization 

Once the KODO for Endpoints server is installed, you have to perform the server initialization. As the `root` user run the following script:

```text
# /opt/storware/kodo-server/api-core/bin/kodo-init.sh
```

Follow the instructions to complete the configuration.

{% hint style="info" %}
You can use the following parameters with the script:

**-p \| --root-password**  
Specify the password for the root database user. If a password is not provided or the root database user password is empty you will be asked to provide it. Default: none

**-k \| --kodo-password**  
Specify the password for the kodo database user. If the password is not provided it will be generated. Default: none

**-h \| --hostname**  
Specify database host address. Default: localhost
{% endhint %}

#### Example:

```text
[root@localhost ~]# /opt/storware/kodo-server/api-core/bin/kodo-init.sh 
Database root user passwod is not set!
Please provide new password for database root user: 
Repeat password: 
Updating root password...
Disabling remote root login...
Removing anonymous users...
Removing test database...
Flushing privileges...
User 'kodo' does not exist.
Creating 'kodo' user...
User password: 3izrxLkLSEzN6eC8spfgHMTtC4joowWX
Database 'storware' does not exist.
Creating 'storware' database...

DONE!
Start KODO server with: systemctl start kodo-server-api-core
[root@localhost ~]#
```

The KODO server initialization script creates the **kodo-for-endpoints** service, which is the main server process. To start the **kodo-for-endpoints** service run:

```text
# systemctl start kodo-for-endpoints
```

Go to the [IBM Spectrum Protect server configuration](spectrum-protect-tsm-configuration.md) section to learn how to prepare and configure the IBM Spectrum Protect server for use with the KODO server.

