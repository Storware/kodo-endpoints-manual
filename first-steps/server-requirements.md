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

* Linux CentOS 7
* Linux CentOS 8
* Red Hat Enterprise Linux 7 
* Red Hat Enterprise Linux 8

### **Hardware requirements**

* Four x86 64bit CPU cores, virtual or physical \(six cores recommended\)
* At least 8 GB RAM \(16GB recommended \)
* Disk space:
  * At least 20GB in installation directory _\(default /opt\)_ \(60GB recommended\)
  * At least 1 TB for backup storage recommended
* At least 1Gbit Ethernet connection \(dedicated 10Gbit port for backup is recommended\)

### Tivoli Storage Manager/Spectrum Protect

IBM Tivoli Storage Manager/Spectrum Protect server instance is required for KODO for Endpoints server to be used as the backup engine. This document doesn't cover the installation and configuration of the IBM Tivoli Storage Manager/Spectrum Protect server.

## KODO for Endpoints server VA support and requirements

### **Supported Hypervisors**

Currently, the following hypervisors are supported:

* ESXi 6.5
* ESXi 6.7

### **Virtual Appliance configuration**

 ****Currently the following hypervisors are supported:

#### KODO for Endpoints Gateway:

* 2 virtual CPUs
* At least6 GB of RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 20 GB     

#### KODO for Endpoints Bundle:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 50 GB
  * HDD2: 20 GB
  * HDD3: 40 GB
  * HDD4: 200GB
  * HDD5: 1TB 

{% hint style="info" %}
All disks can be configured as thin-provisioned_._ This hardware configuration is the minimum recommended configuration for a small/demo/lab environment. Please contact [Storware Support](mailto:support@storware.eu) for recommendations for your production environment.
{% endhint %}

\*\*\*\*

