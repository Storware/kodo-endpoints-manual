# Deploying VA

## Accessing OVA image files <a id="accessing-virtual-machine"></a>

A preconfigured virtual machine appliance in the OVA format is ready to deploy in the VMware virtual environment in version 6.5 or above. You can download KODO for Endpoints VA files from the following site:

​[ftp://ftp.storware.eu/](ftp://kodo4cloud@ftp.storware.eu/)

Use the following credentials to access the FTP server:

**Login:** kodo4endpoints   
**Password:** vF3gDz86pAnD

You can download the following OVA image files:

* **kodo.for.endpoints-gateway-va-4.ova** \(if you want to deploy KODO for Endpoints Gateway\)
* **kodo.for.endpoints-bundle-va-4.ova** \(if you want to deploy KODO for Endpoints Bundle\)

{% hint style="info" %}
Note: Validate the downloaded file by the MD5 hash using the information in the text files, assigned to the OVA images 
{% endhint %}

To deploy KODO for Endpoints server from the OVA file at your virtual environment, follow the instructions below:

* Log in to VMware vCenter/ESXi then click on "Create/Register VM".

![](../../.gitbook/assets/image%20%2868%29.png)

* Select "Deploy OVA Template".

![Enter a name for the virtual machine, and select ova file.](../../.gitbook/assets/image%20%2875%29.png)

* Enter a name for the virtual machine and folder.

![](../../.gitbook/assets/image%20%2866%29.png)

* Select a compute resource

![](../../.gitbook/assets/image%20%2865%29.png)

* Select a compute resource

![](../../.gitbook/assets/image%20%2874%29.png)

* Select storage

![](../../.gitbook/assets/image%20%2881%29.png)

* Select networks.If you would like to synchronize AD/LDAP serwer users, then the network should have access to your local AD/LDAP server.

![](../../.gitbook/assets/image%20%2884%29.png)

* Verify your settings for the OVA teplate and click the **Finish** to start the OVA deployment process.

![](../../.gitbook/assets/image%20%2883%29.png)

*  When the server is deployed, you can power it on. 

1. Connect to your vCenter server using vSphere Web Client, or you can connect directly to your ESXi server.
2. 3. Choose ESX host in the cluster \(and also a resource pool if you are using one\) you would like to deploy the OVA template.
4.  Right-click and select **Deploy OVF template**.
5.  Select **Local file** and browse for the OVA file. Click the **Next** button.
6. Select a name and folder for the virtual machine. Click the **Next** button.
7. Select a compute resource. Click the **Next** button**.**
8. Verify the template details. Click the **Next** button**.**
9. Select the storage for the configuration and disk files \(choose preferred disk type. Note: the virtual machine will utilize about 30 GB on the disk after installation if you select **thick** virtual disk format\). Click the **Next** button.
10.  Select a destination network. If you would like to synchronize AD/LDAP serwer users, then the network should have access to your local AD/LDAP server. Click the **Next** button**.**
11. Click the **Finish** button to start VM creation**.**
12. When the KODO Server VA is deployed, you can power it on. 

If you've downloaded the "**kodo.for.endpoints-gateway-va-4.ova"** image file, after the deployment you have to go to the  [IBM Spectrum Protect engine](../spectrum-protect-tsm-configuration.md) section to get to know how to connect the backup engine to KODO for Endpoints server.

If you have successfully downloaded the OVA file, deploy it in a virtual environment. Note that the IP address of the network adapter is automatically assigned by default by the DHCP protocol.

Go to the [Confugure VA](configuring-va/) chapter to learn how to configure KODO for Endpoints server.

