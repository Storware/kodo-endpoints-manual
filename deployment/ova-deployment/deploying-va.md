# Deploying VA

The KODO Server Virtual Appliance comes as an OVA \(Open Virtualization Appliance\) file. The OVA image file is a template that contains a functional CentOS 7 operating system. To deploy the KODO server OVA file, follow the instructions:

1. Connect to your vCenter Server using vSphere Web Client, or directly to ESXi server.
2. Click on a cluster, ESX host in the cluster, or resource pool you would like to deploy the OVA template.
3.  Right-click and select „**Deploy OVF template**”.
4.  Select „**Local file**” and browse for the OVA file. Click the „**Next**” button.
5. Select a name and folder for the virtual machine. Click the „**Next**” button.
6. Select a compute resource. Click the **„Next”** button**.**
7. Verify the template details. Click the **„Next”** button**.**
8. Select the storage for the configuration and disk files \(choose preferred disk type. Note: the virtual machine will utilize about 30 GB on the disk after installation if you select „**thick**” virtual disk format\). Click the „**Next**” button.
9.  Select a destination network. The chosen network should have access to your local AD server. Click the **„Next”** button**.**
10. Click the **„Finish”** button to start VM creation**.**
11. When the KODO Server VA is deployed, power it on. You can now go to the next chapter and configure  KODO for Endpoints server.



