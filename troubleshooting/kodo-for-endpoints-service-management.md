# kodo-for-endpoints service management

### Starting and stopping kodo-for-endpoints service

There are three dedicated scripts to do some basic tasks on the KODO server. Using them you can stop, start the server, and also check its status.

To use the scripts, you have to be logged in as the `kodo` user. Go to the `/opt/storware/kodo-server/api-core/bin` directory  and execute the scripts:

* **stop.sh** - to stop KODO for Endpoints server
* **start.sh** - to start KODO for Endpoints server
* **status.sh** - to check KODO for Endpoints server status

The KODO server can be also started and stopped the **kodo-for-endpoints** service from the root account.

 ****To start the kodo-for-endpoints service, run the following command:

```text
# systemctl start kodo-for-endpoints
```

{% hint style="info" %}
It may take a few minutes to start service
{% endhint %}

Once started **kodo-for-endpoints** service will be listening on port 8181\(default\) for HTTPS connections.

To stop the kodo-for-endpoints service, run the following command**:**

```text
# systemctl stop kodo-for-endpoints
```



