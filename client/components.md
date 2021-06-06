## KODO for Endpoints client components


Core part of Kodo for endpoints is system service named KodoService.
KodoService is used for Continuous Data Protection process. It tracks all changes in files and directories included by backup policy.
It should have access to all folders and files so KodoService is running on system privileges.

![](../.gitbook/assets/kodoservice.PNG)


## Continuous Data Protection and KodoTemp folder

 Kodo servie uses kernel 
KodoTemp folder normally is on system drive C:\KodoTemp and it is hidden. It is used to copy of protected files after any change.
Thanks to this, a backup version of the file is available after each change, even when there is no Internet access.
All changes will be sent to backup server after restore of network connection.

Size of KodoTemp folder can be set in backup policy.
It is good to setup max folder size to prevent out of space situation on system drive.

