# Left Overs



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

If you have successfully downloaded the OVA file, deploy it in a virtual environment. Note that the IP address of the network adapter is automatically assigned by default by the DHCP protocol.



## Protection statuses <a id="device-statuses"></a>

| **Status** |  | **Description** |
| :--- | :--- | :--- |
| Protected  | ![](../.gitbook/assets/protected.png) | The device is protected according to the assigned policy |
| Not protected ![](../.gitbook/assets/unprotected.png) |  | The device didn't connect with the server within the last "X" days. The number of days is configured at a policy level. |
| Locked ![](../.gitbook/assets/locked.png) |  | The device is locked. The user cannot log in and perform any operations from this device. |

![](../.gitbook/assets/image%20%28105%29.png)

![](../.gitbook/assets/image%20%28109%29.png)



