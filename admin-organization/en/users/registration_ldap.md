# LDAP server users synchronization settings

```text
Navigation: Settings > LDAP
```

The KODO system allows you to synchronize the users whose source is directory services like e.g. Active Directory.

Users synced with directory service can login into KODO application using login and password from directory server.

## To configure users synchronization with the directory service:

1. **Go to settings by clicking on Settings in the top right corner**
2. **Go to tab** `USERS SYNCHRONIZATION`
3. **As source of synchronization \(**`Source type` **\) select:** `LDAP`
4. **Set the Synchronize users switch to On**
5. **Set how many minutes KODO has to synchronize with the LDAP server  \(0 - no synchronization\)**
6. **Save changes with** `SAVE CHANGES`

Next:

1. **Go to settings by clicking on Settings in the top right corner**
2. **Go to the LDAP tab**

Fill in the appropriate fields:

## **USERS & GROUP LDAP SOURCE**

* **Server URL** Directory server ip or domain address
* **Login** Username used for synchronization
* **Domain Prefix** Domain name if different than default
* **Search** Directory service search filter
* **Group filter** LDAP group filter
* **LDAP Auto Synchronization frequency \(minutes\)** Interval between automatic user synchronization, "0" to disable

**NOTE: If you configuring synchronization for the first time before clicking the**  `SAVE CHANGES` **button fill the LDAP user password fields.**

Click on the `SAVE CHANGES` button to confirm your changes.

![](../../.gitbook/assets/ldap%20%282%29.png)

