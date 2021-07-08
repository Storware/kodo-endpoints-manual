---
description: >-
  The following chapter provide an information about operating system and
  hardware requirements for KODO Server and KODO Server VA (Virtual Appliance).
  Please review requirements carefully.
---

# Server requirements

## KODO Server requirements

### **Supported Operating Systems**

The following operating systems are supported:

* Linux CentOS 7.x
* Linux CentOS 8.x Stream
* Red Hat Enterprise Linux 7**.**x
* Red Hat Enterprise Linux 8.x

### **Hardware requirements**

* Four x86 64bit CPU cores, virtual or physical \(six cores recommended\)
* At least 8 GB RAM \(16 GB recommended \)
* Disk space:
  * At least 30 GB  free space for operating system binaries
  * At least 20 GB free space for installation directory _\(default /opt\)_ \(60GB recommended\)
  * At least 1 TB for backup storage recommended
* At least 1Gbit Ethernet connection \(dedicated 10Gbit port for backup is recommended\)

### IBM Spectrum Protect

IBM Spectrum Protect server instance is required for KODO for Endpoints server to be used as the backup engine. This document doesn't cover the installation and configuration of the IBM Spectrum Protect server.

## KODO for Endpoints server VA support and requirements

### **Supported Hypervisors**

Currently, the following hypervisors are supported:

* VMware 6.5
* VMware 6.7
* ESXi 6.5
* ESXi 6.7
* VMware 7

### **Virtual Appliance configuration**

KODO for Endpoints server can be deployed in the following two options:  

#### KODO for Endpoints Gateway:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 30 GB     

#### KODO for Endpoints Bundle:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 50 GB
  * HDD2: 20 GB
  * HDD3: 40 GB
  * HDD4: 200 GB
  * HDD5: 1024 GB 

{% hint style="info" %}
All disks can be configured as thin-provisioned_._ This hardware configuration is the minimum recommended configuration for a small/demo/lab environment. Please contact [Storware Support](mailto:support@storware.eu) for recommendations for your production environment.
{% endhint %}

\*\*\*\*

## Network Requirements

* Internet connection is not required generally, but during the installation `yum` needs to fetch packages from the repositories, so you need at least access to your internal repositories.
* KODO for Endpoints server needs access to AD/LDAP server \(if used\)







