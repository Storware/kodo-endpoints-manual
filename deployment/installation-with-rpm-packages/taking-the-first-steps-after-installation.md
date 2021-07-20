---
description: >-
  After you install KODO components, prepare for the configuration. Using the
  configuration scripts is the preferred method of configuring the KODO server
  instance.
---

# Taking the first steps after the installation

## Configuring firewall

Default KODO server configuration requires two ports open:

**8181/tcp -** for kodo-for endpoints component  


### Opening firewall ports

Run following commands to open firewall ports:

```text
# firewall-cmd --zone=public --add-port=8181/tcp --permanent
# firewall-cmd --complete-reload
```

## Configuring kodo-for-endpoints component

To configure the `kodo-for-endpoints` component run the following script:

```text
# /opt/storware/kodo-server/api-core/bin/kodo-init.sh
```

Follow the instructions to complete the configuration.

{% hint style="info" %}
You can use the following parameters with the script:

**-p \| --root-password**  
Specify the password for the root database user. If a password is not provided or the root database user password is empty you will be asked to provide it. Default: none

**-k \| --kodo-password**  
Specify the password for kodo database user. If the password is not provided it will be generated. Default: none

**-h \| --hostname**  
Specify database host address. Default: localhost
{% endhint %}

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

There are three dedicated scripts to do some basic tasks on KODO server. Using them you can stop, start the server, and also check its status.

To use the scripts, you have to be logged in as the `kodo` user. Go to the directory  `/opt/storware/kodo-server/api-core/bin`   and execute 



**To start the kodo-for-endpoints component run:**

```text
systemctl start kodo-for-endpoints
```

{% hint style="info" %}
It may take few minutes to start service
{% endhint %}

Once started kodo-for-endpoints component will be listening on port 8181\(default\) for HTTPS connections.

**To stop kodo-for-endpoints component run:**

```text
systemctl stop kodo-for-endpoints
```



