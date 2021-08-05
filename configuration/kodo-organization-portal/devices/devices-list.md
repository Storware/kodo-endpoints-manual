# Devices list view

A list of devices is a collection of all registered and protected devices in the system. When a user first logs in to the system using his username and password or uses a "magic link" and the KODO server properly authorizes it, the user's device appears in the device list.

To view the list of registered devices, go to the Device view from the main menu.

![](../../../.gitbook/assets/image%20%2847%29.png)

Devices list table view consist of the following columns:

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

To lock the device and prevent a user from logging in to the system,  you can do this in two ways:

* Click the device name from the available list, click the drop-down menu button from the **Options** column and select the **Lock** option.
* Click on the **Lock** button at the right top corner

## Unlock option

To lock the device and prevent a user from logging in to the system,  you can do this in two ways:

* Click the device name from the available list, click the drop-down menu button from the **Options** column and select the **Unlock** option.
* Click on the **Unlock**  button at the right top corner

## Logs option

Using this option you can download the device's logs.  Download the selected log from the available list by clicking on the red download icon.

![](../../../.gitbook/assets/image%20%28138%29.png)

{% hint style="info" %}
Logs are compressed as the zip files, the file name is constructed as follows: **sentDate\_sentTime.zip**
{% endhint %}

## Upgrade option

If the new KODO client package was uploaded to the server and set as current, in the **Options** menu the **Upgrade** option should appear. 

![](../../../.gitbook/assets/image%20%28133%29.png)

Click the **Upgrade** option to send the information about the new client version to the endpoint. In the **Manage Update Packages for Device** window is the information about the currently installed version and the production version available to upgrade. 

![](../../../.gitbook/assets/image%20%28147%29.png)

The pop-up window with the following information will appear.  

![](../../../.gitbook/assets/image%20%28145%29.png)

Log in to the endpoint, open the KODO user console. There should be a new option available \(**Update**\). Click the option to start the update.

![](../../../.gitbook/assets/image%20%28149%29.png)



## Details options



* **Device information** - Information about the registered device i.e: app version, operating system, manufacturer.

* **Protected Files** - Backup browser allows administrator to restore files from backup when [policy](../policies/general-settings.md) allows it, and option: _Allow administrators to restore user files_ is turned on.

![](../../../.gitbook/assets/backupedfiles.png)

* **Device Events** - Device event log.

## In the Options menu you have additional options to choose from:

* Details
* Edit
* Logs

| **Field** | **Description** |
| :--- | :--- |
| Name | Registered device name |
| User | Device ower |
| Platform | Device operating system |
| Version | a version of the installed KODO client |
| Last backup | Last device backup data and time |
| Policy | Assigned protection policy |
| Protection | Device protection status \(see table below\) |
| Options | Quick action menu |

![](../../../.gitbook/assets/image%20%2860%29.png)

##  <a id="device-statuses"></a>

