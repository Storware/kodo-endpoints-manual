# Initial configuration

When the KODO for Endpoints server has been successfully deployed, the server initial configuration is needed.

Log in to the KODO Admin portal as the `kodoadmin` user using a web browser \(providing the server IP address with 8181 port provided e.g. **https://kodo.server.local:8181**\).

Go to the **Settings** menu and switch to the **General** tab. Enter the **Deployment server name** \(it is the KODO server IP address with the 8181 port added\). 

Next, go to the **Email** tab and complete the email settings. Provide the necessary information for the e-mail server configuration:

* **E-mail address** – address used to send e-mails from the KODO server
* **Login** – user name used to login to e-mail server \(optional if the server requires authentication\)
* **Server address** - IP or DNS name of the e-mail server
* **Port** - the e-mail server port
* **Use SSL** - set to "**on**" if SSL communication is required
* **SSL Port** - TCP Port number used by the SSL SMTP server
* **Require Authentication** - set to “on” if the server requires authentication

Next, go to the **License** tab and upload a valid KODO license.

Go to the **IBM Spectrum Protect** tab and check if there's still a connection with the IBM server \(the status should be "**Connected**"\).

Go to the [Administration](../configuration/) chapter to find out how to administer KODO for Endpoints server.

