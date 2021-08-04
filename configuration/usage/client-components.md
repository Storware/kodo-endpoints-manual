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

## Continuous Data Protection solution

A core part of Kodo for endpoints is a system service named **KodoService**. KodoService is used for the Continuous Data Protection \(CDP\) solution. It enables you to backup your data in real time at a pace that may bring increased protection and convenience to you. It automatically detects and saves each and every change made to your data, so that nothing is left overlooked. These changes can be stored locally or remotely and are readily available for recovery just when you need them. As the solution should have access to all folders and files so **KodoService** is running on SYSTEM privileges.



