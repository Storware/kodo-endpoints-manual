---
description: >-
  KODO is using the enterprise Spectrum Protect (TSM) engine as the backup
  provider. We require a special Spectrum Protect (TSM) configuration. Create a
  configuration in accordance with guidelines.
---

# Spectrum Protect \(TSM\) configuration + policy

## Creating domain, policy and management class

KODO system requires some special Spectrum Protect \(TSM\) configuration. Create a configuration in accordance with guidelines:

Log in to the Spectrum Protect server as an administrator with **SYSTEM** level authority.

Define new dedicated domain, policy and management class for KODO.

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

_TIP: You can change retention settings, also many management classes can be created._

{% hint style="info" %}
TIP: You can change retention settings, also many management classes can be created.
{% endhint %}

## Registering node and administrator

Register new node and update administrator information. Created node and administrator will be used by KODO to manage protected data.

### **Spectrum Protect \(TSM\) &lt; 8.1**

{% hint style="info" %}
**Authority class SYSTEM is mandatory.**
{% endhint %}

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

### **Spectrum Protect \(TSM\) &gt;= 8.1**

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> register admin kodo.COMPANY_NAME client_password
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

