# Common problems

## Server communication error

Check if components is working.

You can check status using this command:  
`/opt/storware/kodo-server/api-core/bin/status.sh`

### Check if firewall doesn't block connections

Check if firewall \(global/on workstation/on server\) doesn't block connections to api-core component, default port: 8181.

### Check if workstation has connection to address configured in Web Admin UI component

Check if workstation used to connect with portal has access to address \(IP or FQDN\) configured in `/opt/storware/kodo-server/web-admin-ui/conf/env.json` file.

You can check this usgin a web browser, provide api-core component address to test connection:  
`https://api-core-address:8181/api/version`

Version of installed component should be displayed.

![Version of installed api-core component](../.gitbook/assets/apiversion.png)

## Support contact - when something went wrong

In case of any installation problems please contact with [Storware Support Team](mailto:support@storware.eu) or one of our local [partners](https://storware.eu/en/partners/).

