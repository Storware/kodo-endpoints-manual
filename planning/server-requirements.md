---
description: >-
  The following chapter provide an information about operating system and
  hardware requirements for KODO Server and KODO Server VA. Please carefully
  review requirements.
---

# Platform requirements

## KODO Server requirements

### **Supported operating systems**

KODO for Endpoints server can be deployed on the following operating systems:

* Linux CentOS 7.x \(Core\)
* Linux CentOS 8.x \(Core\)
* Linux CentOS Stream \(Core\)
* Red Hat Enterprise Linux 7**.**x \(Core\)
* Red Hat Enterprise Linux 8.x \(Core\)

{% hint style="warning" %}
Before KODO for Endpoints installation, please make sure your OS is up-to-date. Use **dnf update** \(or **yum update**\) command if needed. It's recommended to reboot your OS afterward. 
{% endhint %}

{% hint style="warning" %}
It is recommended to have an active Red Hat subscription when KODO software is installed REHL8. Use **yum repolist** command to check your subscription status

The [active Red Hat subscription](https://access.redhat.com/management/products) is required for registering the [RHEL 8](https://www.itzgeek.com/tag/rhel-8) systems. You can also [sign up for 30 days trial](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) which will allow you to download Red Hat Enterprise Linux 8 as well as register your RHEL 8 system with Red Hat for receiving packages and updates. 
{% endhint %}

### **Hardware requirements**

The server hardware requirements will be depending on the size of the organization you are going to protect. Go to the [Sizing guide](sizing-guide/) chapter to learn about recommended server parameters.

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

KODO for Endpoints server can be deployed in the following two configuration options:  

#### KODO for Endpoints Gateway:

The virtual appliance is configured with the following hardware parameters:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 30 GB     

#### KODO for Endpoints Bundle:

The virtual appliance is configured with the following hardware parameters:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 50 GB
  * HDD2: 20 GB
  * HDD3: 40 GB
  * HDD4: 200 GB
  * HDD5: 1024 GB 

{% hint style="info" %}
All disks can be configured as thin-provisioned_._ This hardware configuration is the minimum recommended configuration for a small/demo/lab environment. Please review the [Sizing guide ](sizing-guide/)for recommendations for your production environment.
{% endhint %}

## KODO for Endpoints client requirements

KODO for Endpoints client can be installed on the following operating systems:

* Microsoft Windows 7 32-bit
* Microsoft Windows 7 64-bit
* Microsoft Windows 8 32-bit
* Microsoft Windows 8 64-bit
* Microsoft Windows 8.1 64-bit
* Microsoft Windows 8.1 64-bit
* Microsoft Windows 10 32-bit
* Microsoft Windows 10 64-bit

## Network Requirements

* Internet connection is not required generally, but during the installation`yum` needs to fetch packages from the repositories, so you need at least access to your internal repositories.
* KODO for Endpoints server needs access to AD/LDAP server \(if used\).

