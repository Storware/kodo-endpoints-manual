# Components overwiew

## KODO for Endpoints client components

Kodo for Endpoints client normally creates three folders on system drive:

* C:\Program Files\Storware\Kodo
* C:\ProgramData\Storware\Kodo
* C:\KodoTemp

First folder contains all installation components and files required by Kodo for Endpoint client.

All application settings, Tivoli Storage Manager settings and logs from any client components are in c:\ProgramData\Storware\Kodo folder.

Third folder is a part of Kodo Continous Data Protection function.

## Continuous Data Protection and KodoTemp folder

Core part of Kodo for endpoints is system service named KodoService. KodoService is used for Continuous Data Protection process. It tracks all changes in files and directories included by backup policy. It should have access to all folders and files so KodoService is running on SYSTEM privileges.

![](../.gitbook/assets/kodoservice.PNG)

KodoTemp folder is normally hidden and located on system drive C:\KodoTemp. It is used to copy of protected files after any change. Thanks to this, a backup version of the file is available after each change, even when there is no Internet access. All changes will be sent to backup server after restore of network connection.

Size of KodoTemp folder can be set in backup policy. It is good to setup max folder size to prevent out of space situation on system drive.

