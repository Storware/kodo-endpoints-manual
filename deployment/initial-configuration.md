# Initial configuration

Log in to the KODO Admin portal as the `kodoadmin` user using a web browser \(enter the server IP address with 8181 port provided e.g. **https://kodo.server.local:8181**\).

1. Go to the **Settings** menu and switch to the **General** tab. Enter the **Deployment server name** \(it is the KODO server IP address with the 8181 port added\). 

![](../.gitbook/assets/image%20%2867%29.png)

2. Next, go to the **Email** tab and complete the email settings. Provide the necessary information for the e-mail server configuration:

* **E-mail address** – the address used to send e-mails from the KODO server
* **Login** – the user name used to login to the e-mail server \(optional if the server requires authentication\)
* **Server address** - IP or DNS name of the e-mail server
* **Port** - the e-mail server port
* **Use SSL** - check the box if SSL communication is required
* **SSL Port** - TCP Port number used by the SSL SMTP server
* **Require Authentication** - check the box if the server requires authentication
* **Set Email Server Password**- set the password for the user in the **Login** field 

3. Save the settings and send a test email using **Send Test Email** button.

4. Go to the **License** tab and upload a valid KODO license \(the `license.key` file\). If you don't have one, you can contact the Storware team.

5. Go to the **IBM Spectrum Protect** tab. If you've chosen **KODO for Endpoints Bundle** option, check if there's a connection with the IBM server \(the status should be **Connected**\). 

![](../.gitbook/assets/image%20%2880%29.png)

If you've chosen another KODO for Endpoints server installation option, enter the following settings:

* **Server address -** enter the server address \(you can use **localhost** if you've configured local IBM Spectrum Protect server\) 
* **Port** - set the number at 1502
* **Administrative Port** - set the number at 1503
* **Node name** - it's the node name you've configured in the previous section

6. In the **SET IBM SPECTRUM PROTECT PASSWORD** field, enter the password you've set in the previous section. Click the **Update Password** button to save it. The **Server Connection Status** should be changed to **Connected** \(it may take a while\).  If the status is **Not connected**, please refresh the web browser site.

![](../.gitbook/assets/image%20%2814%29.png)

If you've chosen **KODO for Endpoints Bundle** option, check if there's a connection with the IBM server \(the status should be **Connected**\).

7. Go to the DB Backup, to configure **MariaDB** backup. It can be set to be triggered once a day at a given time. You can also set the number of stored backups.

![](../.gitbook/assets/image%20%2889%29.png)

Go to the [Client deployment section](deployments/) to get to know how to deploy the KODO client application on the endpoints.

