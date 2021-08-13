# Common problems

## Server communication error

If there is a server connection problem, please check the server status. 

Log in as the `kodo` user and execute the following command:

```text
[kodo@kodoserver]$ /opt/storware/kodo-server/api-core/bin/status.sh
API (pid:1618) running.
```

### Check if the firewall doesn't block connections

Check if the firewall \(global/on workstation/on the server\) doesn't block connections to the api-core component, default port: 8181.



```text
[kodo@kodoserver]$ /opt/storware/kodo-server/api-core/bin/status.sh
API (pid:1618) running.
```

### Check the KODO server version

You can check this using a web browser, provide the KODO server IP address test connection:  
`https://kodoserver_IP:8181/api/version`

A version of the installed KODO server should be displayed.

![](../.gitbook/assets/image%20%28182%29.png)

YOu can also check the installed server version using the following command

```text
[kodo@kodoserver]$ curl -k https://localhost:8181/api/version
{"value":"4.1.2-ec10373"}
```

## Support contact - when something went wrong

In case of any installation problems please contact with [Storware Support Team](mailto:support@storware.eu).

