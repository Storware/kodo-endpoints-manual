---
description: >-
  After you install KODO components, prepare for the configuration. Using the
  configuration scripts is the preferred method of configuring the KODO server
  instance.
---

# Taking the first steps after installation

## Configuring firewall

Default KODO server configuration requires two ports open:

**8181/tcp -** for api-core component  
**5000/tcp** - for web-admin-ui component

### Opening firewall ports

Run following commands to open firewall ports:

```text
# firewall-cmd --zone=public --add-port=8181/tcp --permanent
# firewall-cmd --zone=public --add-port=5000/tcp --permanent
# firewall-cmd --zone=public --reload
```

## Configuring api-core component

To configure api-core component run script:

```text
# /opt/storware/kodo-server/api-core/bin/kodo-init.sh
```

Follow the instructions to complete the configuration.

You can use the following parameters with the script:

_-p \| --root-password_  
Specify the password for the root database user. If a password is not provided or the root database user password is empty you will be asked to provide it. Default: none

_-k \| --kodo-password_  
Specify the password for kodo database user. If the password is not provided it will be generated. Default: none

_-h \| --hostname_  
Specify database host address. Default: localhost

#### Example:

```text
[root@localhost ~]# /opt/storware/kodo-server/api-core/bin/kodo-init.sh 
Database root user passwod is not set!
Please provide new password for database root user: 
Repeat password: 
Updating root password...
Disabling remote root login...
Removing anonymous users...
Removing test database...
Flushing privileges...
User 'kodo' does not exist.
Creating 'kodo' user...
User password: 3izrxLkLSEzN6eC8spfgHMTtC4joowWX
Database 'storware' does not exist.
Creating 'storware' database...

DONE!
Start KODO server with: systemctl start kodo-server-api-core
[root@localhost ~]#
```

### Starting and stopping kodo-for-endpoints component

**To start the kodo-for-endpoints component run:**

```text
systemctl start kodo-for-endpoints
```

{% hint style="info" %}
It may take few minutes to start service
{% endhint %}

Once started api-core component will be listening on port 8181\(default\) for HTTPS connections.

**To stop kodo-for-endpoints component run:**

```text
systemctl stop kodo-for-endpoints
```



