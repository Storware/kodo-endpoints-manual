---
description: >-
  The following chapter provide an information about operating system and
  hardware requirements for KODO Server and KODO Server VA. Please carefully review requirements.
---

# KODO Server requirements

## **Supported Operating Systems**

The following operating systems are supported.

* Linux CentOS 7 ( Recommended )
* Linux CentOS 6 
* Red Hat Enterprise Linux 7 ( Recommended )
* Red Hat Enterprise Linux 6

## **Hardware requirements**

* Four x86 64bit CPU cores, virtual or physical ( six cores recommended )
* At least 8 GB RAM ( 16GB recommended )
* Disk space:
  * At least 20GB in installation directory _\(default /opt\)_ ( 60GB recommended )
  * At least 1 TB for backup storage recommended
* At least 1Gbit Ethernet connection ( dedicated 10Gbit port for backup recommended )

## Tivoli Storage Manager/Spectrum Protect

Running Tivoli Storage Manager/Spectrum Protect server instance is required for KODO server. Tivoli Storage Manager / Spectrum Protect is used as backup engine. This document doesn't cover installation or configuration of backup engine.


# KODO Server VA requirements

## **Supported Hypervisors**

The following hypervisors are supported.

* ESXi 5.0
* ESXi 5.1
* ESXi 5.5
* ESXi 6.0
* ESXi 6.5

## **Virtual Appliance hardware requirements**

### KODO Gateway:

* 2 Virtual CPUs
* 6 GB RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 20 GB     

### KODO Bundle:

* 4 virtual CPUs
* 16 GB RAM
* Disk space:
  * HDD1: 16 GB
  * HDD2: 20 GB
  * HDD3: 1TB 

_NOTE: All disk can be configured as thin-provsioned_

_NOTE: This hardware configuration is minimum recommended configuration for small/demo/lab environment. Please contact with_ [_Storware Support_](mailto:support@storware.eu)_. for recommendation for your production environment._


