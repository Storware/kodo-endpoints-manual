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

You can use following parameters with script:

_-p \| --root-password_  
Specify password for root database user. If password is not provided or root database user password is empty you will be asked to provide it. Default: none

_-k \| --kodo-password_  
Specify password for kodo database user. If password is not provided it will be generated. Default: none

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

### Starting and stopping api-core component

**To start api-core component run:**

```text
systemctl start kodo-server-api-core
```

{% hint style="info" %}
It make take few minutes to start service
{% endhint %}

Once started api-core component will listen on port 8181\(default\) for HTTPS connections.

Now you can configure web-admin-ui component that will allows you to mange kodo instance.

**To stop api-core component run:**

```text
systemctl stop kodo-server-api-core
```

## Configuring web-admin-ui component

To configure web-admin-ui component run script:

```text
# /opt/storware/kodo-server/web-admin-ui/bin/web-admin-ui-init.sh -s api-core-url
```

Follow the instructions to complete the configuration.

You need to use following parameter with script:

_-s \| --server_  
Specify HTTPS url to api-core component. Default: none

{% hint style="info" %}
Remember to specify listening port of api-core component
{% endhint %}

#### Example:

```text
[root@localhost ~]# /opt/storware/kodo-server/web-admin-ui/bin/web-admin-ui-init.sh -s https://10.10.0.5:8181
Trying connect to KODO server... [OK]
Trying to obtain KODO api version...[OK] (3.16.0)
Enabling web-admin-ui service...
Created symlink from /etc/systemd/system/multi-user.target.wants/kodo-server-web-admin-ui.service to /etc/systemd/system/kodo-server-web-admin-ui.service.
Starting web-admin-ui service...
DONE!
[root@localhost ~]#
```

Once started api-core component will listen on port 5000 for HTTPS connections.

{% hint style="warning" %}
The server url address \(IP or FQDN\) that you provide in configuration is used in javascript that is executed on local web browser. Web browser needs to be able to connect to it.
{% endhint %}

### Starting and stopping web-admin-ui component

**To start web-admin-ui component run:**

```text
systemctl start kodo-server-web-admin-ui
```

**To stop web-admin-ui component run:**

```text
systemctl stop kodo-server-web-admin-ui
```

