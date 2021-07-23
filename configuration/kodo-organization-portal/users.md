# Users

In the Users view you can find all local users and LDAP users, that are currently available on the KODO server.

![](../../.gitbook/assets/image%20%2846%29.png)

To add a new local user, click the **Add Local User** button and fill in all required fields:

* Username \(in the e-mail format\) 
* First name 
* Last name 
* Company role 
* Phone number 
* Policy  
* Groups 
* Password 
* Confirm Password 

Click the **Save** button to create the user. Check if the user appears on the user list.

In the Users view the following options are available. Please refer to them.

## Deploy Client option

If a new user is added or synchronized, the next step is the client deployment. This options allows to send the deployment email with the installation guide and the "magic link" to a user. The user can follow the links to download the KODO client \(32-bit or 64-bit\) and use the magic link to automatically log in to the KODO server using KODO client console. The user device his is currently logged on wil be added to the device list.

## Lock option

To lock user account, click the **Lock** button. This option locks the user account on the KOD serever, so the backup and restore operations will not be able to peform on the user device. The user also will be automatically logged out from the KODO client console.

## Unlock option

To unlock user account, click the **Unlock** button. This options locks the user account on the KODO server, preventing the backup and restor operations from performing on the user device. The user will also be automatically logged out of the KODO client console.

## Delete option

To delete user account, click the Delete button. This options removes the user account from the KODO server. The user will also be automatically logged out of the KODO client console. If the LDAP user was deleted, the user account will apper again on the user list after the next LDAP user synchronization operation. 

## Synchronize

To synchronize LDAP users, click the **Synchronize** button. The users will be displayed on the user list. If the user account has been locked on the LDAP server, the user account is also locked on the KODO server. 

## Options

In the Options menu the following choices are available:

* Details - to preview the user personal details
* Edit - to change or update user account 
* Delete- to delete user acocunt
* Deploy client - to send an email with installation guide, KODO client download links and the "magic link"



Go to the [Devices ](devices.md)chapter to learn how to manage users devices.







 

