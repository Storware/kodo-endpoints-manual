# Settings

In the **Settings** view, you can configure the main organization settings.

## General tab

### **USAGE & ACTIVITY REPORT**

This section allows you to configure reports about space usage and device activity

**Send reports every \(days\)**  
The interval with which the reports are sent

**Send reports to emails**  
The email addresses to which the report should be sent. Multiple email addresses can be provided \(comma separated\).

**Send report time**  
Time at which the report should be sent.

**Unprotected devices notification time**  
Time at which the report should be sent.

Confirm the settings with the **Save** button.

## Administrators tab

In this tab, you can list and manage your organization's administrators. If you need to add another organization admin, click the **Add Administrator** button.

![](../../.gitbook/assets/image%20%28170%29.png)

Provide all required information to create the new administrator.

![](../../.gitbook/assets/image%20%28166%29.png)

In the **Options** menu, you have the following options to choose from:

* **Reset password**  - to reset administrator's password
* **Edit** - to change the administrator's details like username, email address or phone number
* **Delete**- to remove the administrator account you have to type in his name in the confirmation window. 

![](../../.gitbook/assets/image%20%28174%29.png)

## LDAP tab

The LDAP configuration is described in [Sync users with LDAP](settings.md) chapter.

Before you begin the LDAP server configuration with KODO Organization Admin Portal, on the LDAP server you have to prepare the following resources:

1. A user group \(you can name it e.g: **KODO** to be easy associated with the KODO for Endpoints server.
2. Create a dedicated user 

To configure connection LDAP server with KODO Organization Admin Portal, to as follow:

1. Enter the LDAP server name or IP address.
2. Enter the login \(it 

![](../../.gitbook/assets/ldapset.png)

Provide necessary information:

* **Server URL -** directory server IP or domain address
* **Login -** username used for synchronization
* **Username format -** username and domain format used in LDAP
* **Search -** directory service search filter
* **Group filter -** LDAP group filter



{% hint style="warning" %}
If you configuring synchronization for the first time before clicking the ![](../../.gitbook/assets/savebuttonsmall.png) button fill the LDAP user password fields.
{% endhint %}

Click on the button to confirm your changes.

![](../../.gitbook/assets/image%20%28164%29.png)

## User Synchroziation tab

Here you can configure the source of user synchronization from an external source.

**Source type**  
Source of user synchronization:

* **NONE** - no synchronization with external
* **LDAP** - users synchronization with LDAP service

**Auto synchronize users**  
User synchronization will be performed automatically according to configured frequency \(see below\)

**Auto synchronization frequency \(minutes\)**  
Every how many minutes automatic users synchronization will be performed.

## NOTIFICATIONS

Here you can configure support for users SMS notification about unprotected devices.

**SMS Notification Provider**  
Here you can choose communication way with your SMS gateway. At this moment only e-mail communication is supported.

**Phone number digits to include in notifcation address \(from end\)**  
Phone number is taken from user profile \(_TELEPHONE_ field\). Here you can configure how many digits, counting from the end, should be used to create e-mail message template. Use "0" digit to not trim phone numer at all.

**Address Construction Template**  
User variables to build "from" template e-mail address that will be used to communicate with SMS gateway. You can use following variables:

* **%PHONE%** - user phone number will be used instead

Example:  
_Address Construction Template: %PHONE%@example-sms-gateway.com  
E-mail from address: 123420123@example-sms-gateway.com_

## 

