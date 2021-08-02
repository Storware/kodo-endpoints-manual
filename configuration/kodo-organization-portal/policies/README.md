# Policies

To automatically manage data protection and retention, you have to define a policy, which includes rules that you set through the **KODO Organization portal.** In the policy settings, the administrator can decide what data is stored and how long it is retained and available for restoration to customers and configure many more settings. 

When the KODO server is installed, the Default policy by default is created. You can customize that **Default policy** or create a new one.



A user is assigned to the policy, which protects all his devices according to the settings.



The policy is assigned to a user and protects all his devices according to the settings.

When a server is installed, by default it has one default policy. You can customize that `Default policy` or create a new one.

To view the list of policies, select `Policies` from the main menu.

![](../../../.gitbook/assets/policieslist.png)

The policies list table view consists of the following columns:

| **Field** | **Description** |
| :--- | :--- |
| Name | Name of policy |
| Priority | Priority \(see below\) |
| Users count | Numer of users associated with the policy |
| Date created | Creation date of the policy |
| Created by | Who created policy |
| Date modified | When the policy was modified last time |
| Modified by | Who modified policy |
| Options | Options menu |

## Default policy <a id="default-policy"></a>

The default policy will be used for all new users synced from an external source, like e.g. Active Directory.

## Priority <a id="policy-priotiy"></a>

When the user belongs to the group, group policy will be applied. In case when user belongs to many groups, priority will determine which policy will be applied.

The higher priority, the more important the policy is.

To modify policy priorities, go to the list of policies and then click on `Manage Priority`

Grab the selected policy and move \(grab and drop\) it to the selected position. The higher the policy is, the higher priority will be assigned. Grab policy and move it around the list

![](../../../.gitbook/assets/image%20%2853%29.png)



