---
description: >-
  KODO is using enterprise Spectrum Protect (TSM) engine as backup provider. We
  require special Spectrum Protect (TSM) configuration. Create a configuration
  in accordance with guidelines.
---

# IBM Spectrum Protect server configuration

KODO is using the enterprise IBM Spectrum Protect engine as the backup provider. We require a special IBM Spectrum Protect configuration. Create a configuration in accordance with this guideline.

## Creating domain, policy, and management class

KODO system requires some special IBM Spectrum Protect configuration. Create a configuration in accordance with this guideline:

Log in to the console as the `root` user. Next, you have to log in to the IBM Spectrum Protect server as an administrator with **SYSTEM** level authority. Run the `dsmadmc` command:  

```text
# dsmadmc
IBM Tivoli Storage Manager
Command Line Administrative Interface - Version 7, Release 1, Level 8.8
(c) Copyright by IBM Corporation and other(s) 1990, 2020. All Rights Reserved.

Enter your user id:  admin

Enter your password:

Session established with server KFE: Linux/x86_64
  Server Version 8, Release 1, Level 12.100
  Server date/time: 07/21/2021 11:45:23  Last access: 07/20/2021 15:44:42


tsm: SERVER1>

```

Define new dedicated domain, policy, and management class for KODO.

```text
SERVER1> define domain kodo
SERVER1> define policy kodo kodo
SERVER1> define mgmt kodo kodo 30days
```

Define a new copy group and assign it as default. Remember to change `destination` parameter according to your Spectrum Protect configuration.

```text
SERVER1> define copy kodo kodo kodo destination=POOL_NAME rete=30 reto=30 vere=nol verd=nol 
SERVER1> assign defmgmt kodo kodo 30days
SERVER1> activate policy kodo kodo
```

{% hint style="info" %}
TIP: You can change the retention setting, also the name of the management class.
{% endhint %}

## Registering a new node and administrator account

Register a new node and update administrator information. Created node and administrator will be used by KODO to manage protected data.

### **IBM Spectrum Protect &lt; 8.1**

{% hint style="info" %}
**Authority class SYSTEM is mandatory.**
{% endhint %}

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

### **IBM Spectrum Protect &gt;= 8.1**

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> register admin kodo.COMPANY_NAME client_password
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

Go to the [Initial configuration](initial-configuration.md) chapter to start KODO for Endpoints server configuration.

