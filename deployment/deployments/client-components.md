# Client components

Once the KODO client software was installed, there are some changes made on the user's endpoint. Three application folders are created and the service handling continuous data protection.

## Application folders

Kodo for Endpoints client creates three folders by default on the system drive during the installation process:

* C:\Program Files\Storware\Kodo
* C:\ProgramData\Storware\Kodo
* C:\KodoTemp

The first folder contains all installation components and files required by KODO for Endpoints client.

All application settings, Tivoli Storage Manager settings, and logs from any client components are in c:\ProgramData\Storware\Kodo folder.

The third folder is a part of the KODO **Continuous Data Protection** function.

**KodoTemp** folder is configured as hidden by default and located on system drive **C:\KodoTemp**. It is used to copy protected files after any change. This ensures that a backup version of the file is available after every change, even if there is no Internet access. All changes will be uploaded to the backup server when the network connection is restored.

The size of the KodoTemp folder can be set in the backup policy. It is good practice to set a maximum folder size to prevent running out of space on the system disk.

## Continuous Data Protection service

A core part of Kodo for endpoints is a system service named **KodoService**. KodoService is used for the Continuous Data Protection \(CDP\) process. It tracks all changes in files and directories included by the backup policy. It should have access to all folders and files so KodoService is running on SYSTEM privileges.

![](../../.gitbook/assets/kodoservice.PNG)

