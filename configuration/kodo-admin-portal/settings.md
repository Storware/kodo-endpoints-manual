# Settings

## Settings

To change configuration settings select the **Settings** menu from the left pane and switch to the apropriate tabs.

### **GENERAL**

This section allows you to configure the domain name for URL with the deployment package: ![email](../../.gitbook/assets/deploy.png)

_The link will be sent in the format:_ [https://deployment.server.name/TOKEN](https://deployment.server.name/TOKEN)

You can narrow access for kodoadmin to specific IP addresses.

Confirm the settings with the **Save** button

### Email

In this section, you will configure SMTP server settings for KODO for Endpoint.

To set up an **e-mail** server:

1. Click the **Settings** located in the top bar, this will move you to the KODO configuration page
2. Click the **General** tab.

   1. Provide the necessary information for the e-mail server configuration
      * **E-mail address** – address used to sending e-mails from KODO
      * **Login** – user name used to login to e-mail server \(optional if the server requires authentication\)
      * **Server address** - IP or DNS name of the e-mail server
      * **Port** - port of the e-mail server
      * **Use SSL** - check it  "**on**" if SSL communication is required
      * **SSL Port** - TCP Port number used by the SSL SMTP server
      * **Require Authentication** - set to “on” if the server requires authentication

   ![](../../.gitbook/assets/wert.png) 

3. Click the **Save** buttony
4. If the server needs authentication then provide a password for the e-mail server in the **SET EMAIL SERVER PASSWORD** section.

   ![mail\_password](../../.gitbook/assets/emailpass.png)

5. Click the “**UPDATE PASSWORD**” button

{% hint style="info" %}
_TIP: You can test your configuration click **SEND TEST EMAIL** button_
{% endhint %}

After installation and configuration of SSL components for Spectrum Protect Server described in [IBM Spectrum Protect engine](https://github.com/Storware/kodo-endpoints-manual/tree/48a0e77771612de33ae0394056835a6d98a068de/configuration/deployment/ibm-spectrum-protect/README.md) you can configure SSL settings in KODO Admin portal tab.

## Configuring SSL connection with Spectrum Protect \(TSM\)

To use SSL connection between KODO Server, desktop clients, and Spectrum Protect \(TSM\) server,  you have to upload the correct SP \(TSM\) certificate. This certificate will be used by the server, and also will be distributed to all KODO for Desktop clients and used with SSL connection between the client a backup server.

If you already have a valid certificate file please follow the steps:

1. Click the **Settings** menu.
2. Click the **IBM Spectrum Protect** tab.
3. Click the **Upload certificate** button and select the valid SP \(TSM\) certificate file.

![tsm](../../.gitbook/assets/ssltsmcert.png)

4. Check the **Use SSL** option.

5. Click the "**Save**" button.

### IBM Spectrum Protect \(TSM\) setup

{% hint style="info" %}
**NOTE:** If you are using KODO virtual appliance, please change the "**Server address**" configuration. the "**Server address**" value should point to KODO server IP address that will be available for backup clients. For virtual appliance no further changes are required.
{% endhint %}

To set up connection with backup server:

1. Click **Settings** located in top bar, this will move you to KODO configuration page
2. Click **Spectrum Protect** tab.
3. Provide all necessary Spectrum Protect server settings:
   * **Server address** – IP/DNS name of Spectrum Protect Server
   * **Port** – Spectrum Protect client port
   * **Adminitrative port** – Spectrum Protect Administrative port \(if different from client port\)
   * **Nodename** – a nodname used by KODO \(created in [previous steps](https://github.com/Storware/kodo-endpoints-manual/tree/48a0e77771612de33ae0394056835a6d98a068de/configuration/deployment/spectrum-protect-tsm-configuration.md)\)

     ![tsm](../../.gitbook/assets/ssltsm.PNG)
4. Click the "Save" button.
5. Provide a password for node in “SET IBM SP PASSWORD” section

   ![tsm](../../.gitbook/assets/ssltsmpass%20%281%29.PNG)

6. Click the "**UPDATE PASSWORD"** button

### License registration

After installation or virtual appliance deployment, KODO Server is running in TRIAL mode for 30 days. After that time you need to provide a valid license key.

To get a license key please contact our local [partner](https://storware.eu/en/partners/) or Storware team.

If you already have a valid license key please follow the steps:

1. Click the **Settings** menu.
2. Click the **License** tab.
3. Click the **Upload license** button.
4. Select a license file.
5. Click the "**Open**" button to upload the license.

### Logs

In this tab you can set all parameters for KODO for Endpoints server logs.

1. Click the **Settings** menu. 
2. Provide max number of log files, log level, max size of a single file, and set retention period in days.
3. Click the "**Save**" to apply settings.

![](../../.gitbook/assets/logs.png)

You can download and view server logs as well.

### Billing

In this section, you can assign client licenses to users and set billing period retention.

