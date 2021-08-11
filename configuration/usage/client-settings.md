# Client console menu

## Overview

In the **Overview** view, the basic information about client settings and backup status is displayed:

1. Protection status and last backup \(synchronization\) time.
2. Assigned policy.
3. Continuous Data protection status.
4. The size of the backup data protected to date.

{% hint style="info" %}
You can pause KODO for Endpoints client just by clicking "**Enabled**" and select one from the available options \(15 minutes, 1 hour, 4 hours, or until the next restart\).
{% endhint %}

![](../../.gitbook/assets/clientoverwiew.PNG)

In the **Backups** view, you can browse and recover protected files and folders. You also have a search window \(upper right corner of the window\) to find files by name or extension \(you can use the asterisk as well\).

![](../../.gitbook/assets/image%20%28106%29.png)

To display all available file versions click the watch icon in the **Versions** column.

![](../../.gitbook/assets/image%20%28100%29.png)

You can also use the time slider and the calendar to go to another "**point-in-time**" moment to restore the data you need.

In the **Settings** view you can set:

* **Server**- the IP or the name of the KODO for Endpoint server
* **Language** - you can choose the language Same as Microsoft Windows, English, Českỳ or Polski.
* **Maximum download speed \(kbps\)** 
* **Maximal download speed \(kbps\)**
* **Enable data encryption**- a user can set the password to encrypt backup \(the password will be required during the recovery process\).

![](../../.gitbook/assets/image%20%28117%29.png)

If any previous backups are stored on the KODO server, existing backups will be deleted when encryption is enabled.

![](../../.gitbook/assets/image%20%28120%29.png)

Set a password and confirm it. It takes a while to set up the password.

![](../../.gitbook/assets/image%20%28115%29.png)

![](../../.gitbook/assets/image%20%28113%29.png)



## Backups

{% hint style="info" %}
KODO For Endpoints client will not backup zero-size files!
{% endhint %}

![](../../.gitbook/assets/restore1.png)

On this tab you can perform a restore of files from previous backups.

To restore files or files, just select the day and time of backup on the upper left corner

![](../../.gitbook/assets/callendarclient.png)

and then select a directory and/or file\(s\) to restore. You can restore whole directories instead of individual files too by checking up directories. After selection just click the **Restore** button and choose a restore location.

![](../../.gitbook/assets/restoredestination.png)

After all click one more time the **Restore** button.

If there is a conflict with an existing file, you can choose a restoring action:

![](../../.gitbook/assets/actionrestore.png)

* **Overwrite** - to overwrite all existing files that conflict with restore
* **Skip** - to skip restore of all conflicting files
* **Decide for each file** - decide what to do on every restored file
* **Cancel** - for cancel operation.

![](../../.gitbook/assets/restoring.png)

The operation may be canceled by clicking the **Cancel** button.

Click the **Done** button to finish. The restore process is finalized.

![](../../.gitbook/assets/done.png)

## Settings

On the Settings tab you can change server settings, interface language and turn on or off data encryption.

After changing values just click the **Save** button.

To restore previous values click the **Reset** button.

On this tab you can open thelogs folder for troubleshooting by clicking "_**Open Log folder**_" at the bottom right corner.

![](../../.gitbook/assets/kodosettings.png)

* To enable data encryption just check the box and confirm the warning message.

{% hint style="info" %}
Enabling or disabling of encryption will erase all previously created backups!
{% endhint %}

![](../../.gitbook/assets/encrwarning.PNG)

And set encryption password.

![](../../.gitbook/assets/encryptpass.PNG)

After that backup will be encrypted.

* To disable encryption just unselect the checkbox, confirm the warning message and provide a previously set password.

![](../../.gitbook/assets/decryptwarn.PNG)

![](../../.gitbook/assets/decryptpass.PNG)

