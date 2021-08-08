# Devices list view

A list of devices is a collection of all registered and protected devices in the system. When a user first logs in to the system using his username and password or uses the "magic link" and the KODO server properly authorizes it, the user's device will appear on the **Devices** list.

![](../../../.gitbook/assets/image%20%2847%29.png)

Devices list table view consists of the following columns:

* **Device Name** -registered device name
* **Type** -the type of the device
* **User** - the name of the device owner
* **Platform** - the type of operating system platform represented by an icon
* **KODO client version** - version of the KODO client application installed on the device
* **Last Backup** - date of the last device backup
* **Policy**  -protection policy assigned to the device
* **Protection** -current protection status.
* **Options** - quick action menu for choosing options 

## Lock option

To lock the device and prevent a user from logging in to the system,  you can do this in three ways:

* Click the device name from the available list, click the drop-down menu button from the **Options** column and select the **Lock** option.
* Click on the **Lock** button at the right top corner
* Click the device name and in the **Device Details** windows click the **Lock Device** button.

## Unlock option

To lock the device and prevent a user from logging in to the system,  you can do this in two ways:

* Click the device name from the available list, click the drop-down menu button from the **Options** column and select the **Unlock** option.
* Click on the **Unlock**  button at the right top corner.
* Click the device name and in the **Device Details** windows click the **Unlock Device** button.

## Upgrade option

If the new KODO client package was uploaded to the server and set as current, in the **Options** menu the **Upgrade** option should appear. 

![](../../../.gitbook/assets/image%20%28133%29.png)

Click the **Upgrade** option \(or using the **Upgrade** button\)  to send the information about the new client version to the endpoint. In the **Manage Update Packages for Device** window is the information about the currently installed version and the production version available to upgrade. 

![](../../../.gitbook/assets/image%20%28152%29.png)

The pop-up window with the following information will appear.  

![](../../../.gitbook/assets/image%20%28146%29.png)

Log in to the endpoint, open the KODO user console. There should be a new option available \(**Update**\). Click the option to start the update.

![](../../../.gitbook/assets/image%20%28157%29.png)

## Logs option

Using this option you can download the device's logs.  Download the selected log from the available list by clicking on the red download icon.

![](../../../.gitbook/assets/image%20%28138%29.png)

{% hint style="info" %}
Logs are compressed as the zip files, the file name is constructed as follows: **sentDate\_sentTime.zip**
{% endhint %}

## Archive option

If there's no need to protect the device anymore \(e.g. an employee has left the organization\), it can be switched to the archive mode. 

 



## Details options

To see device details info, click the device name in the **Devices** view or select the **Details** from the **Options** menu.

![](../../../.gitbook/assets/image%20%28151%29.png)

 ****At the top of the **Device Details** window you can find the following information about the device:

* Platform
* Status
* Policy
* Data

In the **Device information** section, you can find information about the registered device i.e.: KODO Client version, manufacturer, model, device ID, operating system, and owner.

In the **Protected Files** section, you can manage the data of the device. You can either delete data from a backup or just restore it.

![](../../../.gitbook/assets/image%20%28156%29.png)

To delete data from a backup, select the item and click **Delete From Backup** \(this will be highlighted when you select the item \(or items\) to delete\). The following confirmation window will appear. Click **Yes** to delete selected data.

![](../../../.gitbook/assets/image%20%28149%29.png)

{% hint style="info" %}
The organization administrator is allowed to restore files from backup when the backup policy allows it, and the option: _**Allow administrators to restore user files**_ ****is turned on.
{% endhint %}

To restore from a backup, select the item and click **Restore From Backup** \(this will be highlighted when you select the item \(or items\) to restore\).

The following confirmation window will appear. Click **Yes** to start the restoration process. 

![](../../../.gitbook/assets/image%20%28154%29.png)

The restored data will be in the ZIP file format and will be available at the [Restore Jobs](../restore-jobs.md) view.

You can also use the **Search Bar** to find a file to restore \(by its name or exetention\) and use the **Point in time** option.



* **Device Events** - Device event log.

##  <a id="device-statuses"></a>

