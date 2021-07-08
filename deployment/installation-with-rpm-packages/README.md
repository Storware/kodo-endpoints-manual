---
description: The RPM packages are suitable for installation on Red Hat and CentOS.
---

# RPM packages installation

{% hint style="info" %}
The commands described below need to be executed with root user privileges.
{% endhint %}

Prior to KODO server installation, you have to add some packages repositories have to be added. Follow the tasks described below to add some required repositories. 

### Add Storware repository

Log in to the server as the `kodo`user and switch to the `root`user.

```text
$ sudo -s
```

When asked for a password use password for `kodo`user.

Create a new repository file: `touch /etc/yum.repos.d/kodo-endpoints.repo`

Copy and paste the following entry into the kodo-endpoints.repo file:

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

To install KODO for Endpoints server you need to install  `kodo-for-endpoints` component. Follow the steps below to start the installation process: 

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

Go to the Taking the first steps the installation chapter to learn what steps are required to configure KODO for Endpoints server. 

