---
description: The RPM packages are suitable for installation on Red Hat and CentOS.
---

# Installation with RPMs

The RPM packages are suitable for installation on Red Hat and CentOS operating systems.

{% hint style="warning" %}
This type of installation requires the usage of an external IBM Spectrum Protect server.
{% endhint %}

{% hint style="info" %}
The commands described below need to be executed with the `root` user privileges.
{% endhint %}

If you've prepared a virtual or physical machine to install KODO for Endpoints server, you have to configure some software repositories before you install KODO main component. 

Follow the tasks described below to add some required repositories. 

### Add Storware repository

Log in to the server as the `kodo`user and switch to the `root`user.

```text
$ sudo -s
```

Use the `kodo`user if asked for it.

Create a new repository file: `touch /etc/yum.repos.d/kodo-endpoints.repo`

Copy and paste the following entry into the `kodo-endpoints.repo` file:

```text
[kodo-endpoints]
name=Storware repository
baseurl=https://repo.storware.eu/kodo-endpoints/current
enabled=1
gpgcheck=0
```

### Add MariaDB repository

Create a new repository file: `touch /etc/yum.repos.d/MariaDB.repo`

Copy and paste the following entry into the MariaDB.repo file:

```text
# MariaDB 10.5 CentOS repository list - created 2021-07-01 13:34 UTC
# http://downloads.mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.5/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

Go to the next step to start KODO for Endpoint server installation.

## Installation

To install KODO for Endpoints server you need to install `kodo-for-endpoints` component. Follow the steps below to start the installation process: 

1. Log in as the root user.
2. Use the command below to install `kodo-for-endpoints` package.

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

KODO server configuration requires opening port 8181/tcp. To open it from the console, do the following steps:   

**8181/tcp -** for kodo-for endpoints component

### Opening firewall ports

Log in to the console as the root user. Run following commands to open firewall ports:

```text
# firewall-cmd --zone=public --add-port=8181/tcp --permanent
# firewall-cmd --complete-reload
```

## Configuring kodo-for-endpoints component

To configure the `kodo-for-endpoints` component,  run the following script to initialize KODO server:

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

### Starting and stopping kodo-for-endpoints component

There are three dedicated scripts to do some basic tasks on KODO server. Using them you can stop, start the server, and also check its status.

To use the scripts, you have to be logged in as the `kodo` user. Go to the directory  `/opt/storware/kodo-server/api-core/bin`   and execute the scripts:

* **stop.sh** - to stop KODO for Endpoints server
* **start.sh** - to start KODO for Endpoints server
* **status.sh** - to check KODO for Endpoints server status

The KODO server can be also started and stopped the **kodo-for-endpoints** service from the root account.

 ****To start the kodo-for-endpoints component, a the `root` user  run:

```text
# systemctl start kodo-for-endpoints
```

{% hint style="info" %}
It may take a few minutes to start service
{% endhint %}

Once started kodo-for-endpoints component will be listening on port 8181\(default\) for HTTPS connections.

To stop the kodo-for-endpoints component, run the following command**:**

```text
# systemctl stop kodo-for-endpoints
```

Go to the [IBM Spectrum Protect server configuration](../spectrum-protect-tsm-configuration.md) chapter to find out how to configure it to be able to use it with KODO server. 

