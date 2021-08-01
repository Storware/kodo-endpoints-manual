# Client components

## KODO for Endpoints client folders

Kodo for Endpoints client creates three folders by default on the system drive during the installation process:

* C:\Program Files\Storware\Kodo
* C:\ProgramData\Storware\Kodo
* C:\KodoTemp

The first folder contains all installation components and files required by KODO for Endpoints client.

All application settings, IBM Spectrum Protect Server settings and logs from any client components are in c:\ProgramData\Storware\Kodo folder.

The third folder is a part of the KODO Continuous Data Protection function.

KodoTemp folder is configured as hidden by default and located on system drive **C:\KodoTemp**. It is used to copy protected files after any change. Thanks to this, a backup version of the file is available after each change, even when there is no Internet access. All changes will be sent to the backup server when the network connection is restored.

The size of the KodoTemp folder can be set in the backup policy. It is good practice to set a maximum folder size to prevent running out of space on the system disk.

## Continuous Data Protection service

A core part of Kodo for endpoints is a system service named **KodoService**. KodoService is used for the Continuous Data Protection \(CDP\) process. It tracks all changes in files and directories included by the backup policy. It should have access to all folders and files so **KodoService** is running on SYSTEM privileges.

## KODO client user console

In the **Overview** view, the basic information about client settings and backup status is displayed:

1. Protection status and last backup \(synchronization\) time.
2. Assigned policy.
3. Continuous Data protection status.
4. The size of the backup data protected to date.

{% hint style="info" %}
You can pause KODO for Endpoints client just by clicking "**Enabled**" and select one from the available options \(15 minutes, 1 hour, 4 hours, or until the next restart\).
{% endhint %}

![](../../.gitbook/assets/clientoverwiew.PNG)

If you click the assigned policy name, you can modify the policy from the endpoint level. If in the policy settings \(at the **General** tab\) the **Allow user to modify policy** option is set, to active, then you can choose the applications to be protected \(the extensions for Office, Photos, Music, Video files are included\), the locations \(My Documents and Desktop\) and email client archives \(MS Outlook and IBM Notes\).

![](../../.gitbook/assets/image%20%28117%29.png)

In the **Advanced tab**, you can add the additional directory to be protected \(add file extensions and assign a policy by your choice\) by clicking the **Add Include Directory** button. The chosen directory can be deleted by clicking the "**x**" beside the entry.

![](../../.gitbook/assets/image%20%2899%29.png)

You can also add some directories to be excluded from the policy. Click the **Add Exclude Directory** button to add a directory to be excluded from the backup policy.

In the Backups view, you can browse and recover protected files and folders. You also have a search window \(upper right corner of the window\) to find files by name or extension \(you can use the asterisk as well\).

![](../../.gitbook/assets/image%20%28102%29.png)

To display all available file versions click the watch icon in the Versions column.

![](../../.gitbook/assets/image%20%28100%29.png)

You can also use the time slider and the calendar to go to another "point-in-time" moment to restore the data you need.

In the **Settings** view you can set:

* **Server**- the IP or the name of the KODO for Endpoint server
* **Language** - you can choose the language Same as Microsoft Windows, English, Českỳ or Polski.
* **Maximum download speed \(kbps\)** 
* **Maximal download speed \(kbps\)**
* **Enable data encryption**- a user can set the password to encrypt backup \(the password will be required during the recovery process\).

![](../../.gitbook/assets/image%20%28112%29.png)

If any previous backups are stored on the KODO server, existing backups will be deleted when encryption is enabled.

![](../../.gitbook/assets/image%20%28116%29.png)

Set a password and confirm it. It takes a while to set up the password.

![](../../.gitbook/assets/image%20%28110%29.png)

![](../../.gitbook/assets/image%20%28108%29.png)



