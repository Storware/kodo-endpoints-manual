---
description: The RPM packages are suitable for installation on Red Hat and CentOS.
---

# RPM packages installation

{% hint style="info" %}
The commands described below need to be executed with root user privileges.
{% endhint %}

## Preparation

### Add Storware repository

Create a new repository file: `touch /etc/yum.repos.d/kodo-endpoints.repo`

Copy and paste this into a kodo-endpoints.repo file:

```text
[kodo-endpoints]
name=Storware repository
baseurl=https://repo.storware.eu/kodo-endpoints/current
enabled=1
gpgcheck=0
```

### Add MariaDB repository

Create a new repository file: `touch /etc/yum.repos.d/MariaDB.repo`

Copy and paste this into a MariaDB.repo file:

```text
# MariaDB 10.5 CentOS repository list - created 2021-07-01 13:34 UTC
# http://downloads.mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.5/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

## Installation

To install KODO for Endpoints you need to install  `kodo-for-endpoints` component. Follow the steps below to start the installation process: 

1. Log in as the root user.
2. Use the command below to install kodo-for-endpoints component

```text
# yum install kodo-for-endpoints        
```

The installation process starts. Select "y" when asking about GPG key:

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

Go to the next chapter to learn what are the first steps after the installation. 



