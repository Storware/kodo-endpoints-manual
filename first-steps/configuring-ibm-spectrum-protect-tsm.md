# Configuring IBM Spectrum Protect \(TSM\)

KODO system require some special Spectrum Protect \(TSM\) configuration. Create a configuration in accordance with guidelines:

Log in to the Spectrum Protect server as administrator with **SYSTEM** level authority.

Define new dedicated domain, policy and managment class for KODO.

```text
SERVER1> define domain kodo
SERVER1> define policy kodo kodo
SERVER1> define mgmt kodo kodo 30days
```

Define new copy group and assign it as default. Remember to change `destination` paramater accroding to your Spectrum Protect configuration.

```text
SERVER1> define copy kodo kodo kodo destination=POOL_NAME rete=30 reto=30 vere=nol verd=nol 
SERVER1> assign defmgmt kodo kodo kodo
SERVER1> activate policy kodo kodo
```

_TIP: You can change retention settings, also many management classes can be created._

Register new nodename and update administrator information. This node and administrator will by use by KODO to manage protected data.

**REGISTERING NEW NODE AND ADMINISTRATOR FOR TSM/Spectrum Protect &lt; 8.1**

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

**REGISTERING NEW NODE AND ADMINISTRATOR FOR Spectrum Protet &gt;= 8.1**

```text
SERVER1> register node kodo.COMPANY_NAME client_password dom=kodo maxnummp=100 dedup=client backdel=yes passexp=0
SERVER1> register admin kodo.COMPANY_NAME client_password
SERVER1> update admin kodo.COMPANY_NAME passexp=0
SERVER1> grant authority kodo.COMPANY_NAME cl=sys
```

**Authority class SYSTEM is mandatory.**

