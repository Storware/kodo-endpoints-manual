# Deploying VA

## Accessing OVA image files <a id="accessing-virtual-machine"></a>

The pre-configured virtual machine appliance in OVA format is ready for deployment in a VMware virtual environment version 6.5 or higher. You can download files from the following site:

​[ftp://ftp.storware.eu/](ftp://kodo4cloud@ftp.storware.eu/)

Use the following credentials to access the FTP server:

**Login:** kodo4endpoints   
**Password:** vF3gDz86pAnD

You can download the following OVA image files:

* **kodo.for.endpoints-gateway-va-4.ova** \(to deploy KODO for Endpoints Gateway\)
* **kodo.for.endpoints-bundle-va-4.ova** \(to deploy KODO for Endpoints Bundle\)

{% hint style="info" %}
Note: Please validate the downloaded file by the MD5 hash using the information in the text files, assigned to the OVA images. If you downloaded the file to the  Windows system, use the `certutil` command.
{% endhint %}

## Deploying OVA image file <a id="accessing-virtual-machine"></a>

To deploy KODO for Endpoints server from the OVA file at your virtual environment, follow the instructions below:

1. Log in to VMware vCenter/ESXi, select a datacenter,  a cluster, or a  host, and right-click on the "**Deploy OVF Template**".

![](../../.gitbook/assets/image%20%2897%29.png)

2. Select an OVF Template \(use the "Local file" option and go to the location the file was downloaded\).

![](../../.gitbook/assets/image%20%2892%29.png)

3. Select a name and folder the virtual machine is to be deployed.

![](../../.gitbook/assets/image%20%2870%29.png)

4. Select a compute resource

![](../../.gitbook/assets/image%20%2866%29.png)

5. Review details

![](../../.gitbook/assets/image%20%2876%29.png)

6. Select storage

![](../../.gitbook/assets/image%20%2888%29.png)

* Select networks. If you would like to synchronize AD/LDAP server users, then the network should have access to your local AD/LDAP server.

![](../../.gitbook/assets/image%20%2885%29.png)

7. Verify your settings for the OVA template and click the **Finish** button to start the OVA deployment process.

![](../../.gitbook/assets/image%20%2884%29.png)

8. When the server is deployed, you can power it on. 

If you've deployed the "**kodo.for.endpoints-gateway-va-4.ova"** OVA image file, after the deployment process you have to go to the  [IBM Spectrum Protect server configuration](../spectrum-protect-tsm-configuration.md) section to connect the IBM Spectrum Protect server to KODO for Endpoints server.

Go to the [Configuring VA](configuring-va/) chapter to learn how to configure KODO for Endpoints server.

