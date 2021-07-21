# Administration levels

KODO for Endpoints server was designed in a multi-tenancy architecture. It means that you can define multiple organizations \(tenants\) within one instance of KODO for Endpoints server. In each organization instance, you can backup a separate set of endpoints you defined. 

To be able to administer the server using different levels of access, KODO server was designed to leverage  two administration levels:

* **KODO administration level** - accessed through KODO Admin Portal
* **KODO organization administration level** - accessed through KODO organization portal

Please find the description for each administration level below.

## KODO administrator level

KODO administration level is the highest level of authorization. If you log in to the portal as `kodoadmin` user,  you can configure system settings and other system assets as follow:

* Download or upload installer packages
* Manage administrators
* Manage KODO organizations
* Configure system settings:
  * E-mail server settings
  * IBM Spectrum Protect server settings
  * Licensing information
  * Billing settings
  * DB backup configuration

## KODO organization administrator level

KODO system allows your company to create multiple organizations under one KODO server. Every organization is a separate entity with separated data, settings, users, policies, etc. As the organization administrator you can configure the following system assets:

* Users
* Devices
* Policies
* Deployment
* Organization administrators
* LDAP connection
* Users synchronization
* Notifications
* Usage and activity report

The default organization is named “**My organization**” which is created during KODO for Endpoint server deployment.

{% hint style="info" %}
You can change the default organization name after logging on to the system as KODO administrator. Go to the Organizations menu and click the edit button located in the organization name row.
{% endhint %}

### Default login credentials

{% hint style="info" %}
Here are credentials for two predefined administrator accounts:

* default global admin: `kodoadmin`with password `k0do@dmin` 
* default organization admin: `admin`with password`k0do@dmin`
{% endhint %}

First, you have to log in to the server as `kodoadmin` user and add KODO license to enable full functionality of the server.



