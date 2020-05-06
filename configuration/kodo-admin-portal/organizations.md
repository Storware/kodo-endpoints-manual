# Configuring Web Admin UI

## Configuring connection with api-core <a id="configuring-connection-with-api-core"></a>

You must configure address \(IP or FQDN\) and port of api-core component to which web admin UI will be connecting.

The address \(IP or FQDN\) that you provide in configuration is used with javascript that is executed on local web browser \(on administrator workstation\). So web browser \(administrator host\) need to be able to connect it.

Edit `/opt/storware/kodo-server/web-admin-ui/conf/env.json` file and modify ApiServer line, providing address of api-core component in `https://api-core-addres/api` format.

### Example of env.json file: <a id="example-of-env-json-file"></a>

```javascript
{ 
    "ApiServer" : "https://192.168.0.100:8181/api",     
    "Logging": 
    {         
        "LogLevel": 
        {             
            "Default": "Warning"         
            }     
        } 
    }
```

_In this example administrator workstation from where he will be log in to KODO administrative portal must be able to connect to 192.168.0.100 address_

## Starting web admin UI instance <a id="starting-web-admin-ui-instance"></a>

To start KODO web admin UI instance execute following command: `/opt/storware/kodo-server/web-admin-ui/bin/start.sh`

## Stoping web admin UI instance <a id="stoping-web-admin-ui-instance"></a>

To stop KODO web admin UI instance execute following command: `/opt/storware/kodo-server/web-admin-ui/bin/stop.sh`

## Checking web admin UI status <a id="checking-web-admin-ui-status"></a>

To check KODO web admin UI instance status execute following command: `/opt/storware/kodo-server/web-admin-ui/bin/status.sh`

