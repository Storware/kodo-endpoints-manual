---
description: >-
  The following chapter provides information about the operating system and
  hardware requirements for KODO Server and KODO Server VA (Virtual Appliance).
  Please review the requirements carefully.
---

# Server requirements

## KODO Server requirements

### **Supported Operating Systems**

KODO for Endpoints server can be deployed on the following operating systems:

* Linux CentOS 7.x
* Linux CentOS 8.x Stream
* Red Hat Enterprise Linux 7**.**x
* Red Hat Enterprise Linux 8.x

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

The VA is configured with the following server parameters:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 30 GB     

#### KODO for Endpoints Bundle:

The VA is configured with the following server parameters:

* 4 virtual CPUs
* 16 GB of RAM
* Disk space:
  * HDD1: 50 GB
  * HDD2: 20 GB
  * HDD3: 40 GB
  * HDD4: 200 GB
  * HDD5: 1024 GB 

{% hint style="info" %}
All disks can be configured as thin-provisioned_._ This hardware configuration is the minimum recommended configuration for a small/demo/lab environment. Please review the [Sizing guide chapter](sizing-guide/) for recommendations for your production environment.
{% endhint %}

## Network Requirements

* Internet connection is not required generally, but during the installation`yum` needs to fetch packages from the repositories, so you need at least access to your internal repositories.
* KODO for Endpoints server needs access to AD/LDAP server \(if used\)

