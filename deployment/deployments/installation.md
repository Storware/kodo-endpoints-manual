# First time log in

A user can use the KODO client console to connect to the KODO server using:

* domain user account
* local user account 
* KODO "magic link" 

## **Domain user account**

To use the application, the user must be authenticated on the KODO server. To do this, start the application for the first time \(using the **Kodo** icon on the user's desktop\) and fill in the following configuration fields:

* **Server-** enter the KODO server address in your organization \(with 8181 port\)
* **Username -**enter the user name as "_**domain\username**_" or "**domain@username** \(it depends on the username format set at the LDAP settings at the **Settings** view\)
* **Password-** enter the domain user password. 

Optionally, check the "**Remember me**" option \(the user password will be saved\). Click the **Log in** button. 

![](../../.gitbook/assets/image%20%2877%29.png)

The user will be asked about backup encryption if the **Data encryption** option is enabled at the policy the user is assigned.

![](../../.gitbook/assets/image%20%2878%29.png)

After successful logging, the device is added to the devices list on the server. The backup process will start immediately and the first full backup will be performed. 

## **Local user account**

The local user is created by the organization administrator on the KODO server. Provide the following information in the logging window fields: 

* **Server-** enter the KODO server address in your organization \(with 8181 port\)
* **Username -**enter the local user name \(the defined e-mail address during the user creation process\)
* **Password-** enter the user password. 

Optionally, check the **Remember me** option \(the user password will be saved\). Click the **Log in** button.

## **Magic Link**

If an organization administrator has sent a deployment email, it contains a "magic link" shortcut with which a user \(local or domain\) can be authorized on the KODO server. The user should click the "magic link" to be automatically logged in to the KODO server.

{% hint style="info" %}
After the installation and log in the process of securing the files in the selected locations will begin automatically according to the assigned policy.
{% endhint %}

{% hint style="info" %}
If there was a previous installation of KODO for Endpoints, the total content of **C:\ProgramData\Storware\Kodo** should be removed before the installation!
{% endhint %}

