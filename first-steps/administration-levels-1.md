# Administration levels

KODO for Endpoints server was designed in a multi-tenancy architecture. It means that you can define multiple organizations \(tenants\) within one instance of KODO for Endpoints server. In each organization instance, you can backup a separate set of endpoints you defined. 

To be able to administer the server using different levels of access, the KODO server was designed to leverage two administration levels:

* **KODO administration level** - accessed through KODO Admin Portal
* **KODO organization administration level** - accessed through KODO Organization portal

Please find the description for each administration level below.

## KODO administration level

KODO administration level is the highest level of authorization. If you log in to the portal as `kodoadmin` user you gain an access to the KODO Admin Portal.  From this portal you can configure global system settings and other assets as follow:

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

KODO system allows your company to create multiple organizations under one KODO server. Every organization is a separate entity with separated data, settings, users, policies, etc. If you log in as the `admin` user, you gain an access to the KODO Organization portal. As the organization administrator you can configure the system assets like:

* Users
* Devices
* Policies
* Deployment
* Organization administrators
* LDAP connection
* Users synchronization
* Notifications
* Usage and activity report

The default organization name is “**My organization**”. It is created during KODO for Endpoints server deployment.

{% hint style="info" %}
You can change the default organization name after logging on to the system as the `admin` user. Go to the Organizations menu and click the edit button located in the organization name row.
{% endhint %}

### Default login credentials

{% hint style="info" %}
Here are credentials for two predefined administrator accounts:

* default global admin: `kodoadmin`with password `k0do@dmin` 
* default organization admin: `admin`with password`k0do@dmin`
{% endhint %}

The credentials will be required later in the [Initial configuration](../deployment/initial-configuration.md) chapter. 

Go to the [Planning ](../planning/)chapter to plan your KODO for Endpoints deployment and choose a configuration that fits your organization's protection needs.

