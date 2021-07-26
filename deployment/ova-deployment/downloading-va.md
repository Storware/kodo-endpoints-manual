# Deploying VA

## Accessing OVA image files <a id="accessing-virtual-machine"></a>

A preconfigured virtual machine appliance in the OVA format is ready to deploy in the VMware virtual environment in version 6.5 or above. You can download KODO for Endpoints VA files from the following site:

​[ftp://ftp.storware.eu/](ftp://kodo4cloud@ftp.storware.eu/)

Use the following credentials to access the FTP server:

**Login:** kodo4endpoints   
**Password:** vF3gDz86pAnD

You can download the following OVA image files:

* **kodo.for.endpoints-bundle-va-4.ova** \(if you want to deploy KODO for Endpoints Bundle\)
* **kodo.for.endpoints-gateway-va-4.ova** \(if you want to deploy KODO for Endpoints Gateway\)

{% hint style="info" %}
Note: Validate the downloaded file by the MD5 hash using the information in the text files, assigned to the OVA images 
{% endhint %}

To deploy KODO for Endpoints server from the OVA file at your virtual environment, follow the instructions below:

1. Connect to your vCenter server using vSphere Web Client, or you can connect directly to your ESXi server.
2. Choose ESX host in the cluster \(and also a resource pool if you are using one\) you would like to deploy the OVA template.
3.  Right-click and select **Deploy OVF template**.
4.  Select **Local file** and browse for the OVA file. Click the **Next** button.
5. Select a name and folder for the virtual machine. Click the **Next** button.
6. Select a compute resource. Click the **Next** button**.**
7. Verify the template details. Click the **Next** button**.**
8. Select the storage for the configuration and disk files \(choose preferred disk type. Note: the virtual machine will utilize about 30 GB on the disk after installation if you select **thick** virtual disk format\). Click the **Next** button.
9.  Select a destination network. The chosen network should have access to your local AD server. Click the **Next** button**.**
10. Click the **Finish** button to start VM creation**.**
11. When the KODO Server VA is deployed, power it on. 

{% hint style="warning" %}
If you've downloaded the "**kodo.for.endpoints-gateway-va-4.ova"** image file, after the deployment you have to go to the  [IBM Spectrum Protect engine](../spectrum-protect-tsm-configuration.md) chapter to get to know how to connect the backup engine to KODO for Endpoints server.
{% endhint %}

If you have successfully downloaded the OVA file, deploy it in a virtual environment. Note that the IP address of the network adapter is automatically assigned by default by the DHCP protocol.







Go to the [Deploy VA]() chapter to learn how to install KODO for Endpoints server using downloaded the OVA image file.

