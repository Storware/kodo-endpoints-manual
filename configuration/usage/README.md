# Endpoint client

KODO for Endpoints client is an application designed to backup and restore data from client devices \(laptops/desktops\) running the Windows operating system.

{% hint style="info" %}
MacOS client is currently available only in technical preview mode.
{% endhint %}

The application utilizes Data Protection \(CDP\) which provides comprehensive protection for all information and is able to provide the most optimal and secure access to corporate/private data.

The KODO for Endpoints client application has exceptional and unique features that address the issues that exist in every organization:

* Continuous data protection \(CDP\) 
* Incremental backup
* File versioning 
* Deduplication and compression on the source \(endpoint\)
* "Right-click" approach restore for files
* "Point-in-time" restore
* Privacy policy, integration with IBM Spectrum Protect.
* User data encryption 

![](../../.gitbook/assets/clientoverwiew.PNG)

At the **Overview** view, the basic information about client settings and backup status is displayed:

1. Protection status and last backup \(synchronization\) time.
2. Assigned policy.
3. Continuous Data protection status.
4. Size of the backup data protected so far. 

{% hint style="info" %}
You can pause KODO for Endpoints client just by clicking "**Enabled**" and select one from the available options \(15 minutes, 1 hour, 4 hours, or until the next restart\).
{% endhint %}

If you click the assigned policy name, you can modify the policy from the endpoint level. If in the policy settings \(at the **General** tab\) the **Allow user to modify policy** option is set, to active, then you can choose the applications to be protected \(the extensions for Office, Photos, Music, Video files are included\), the locations \(My Documents and Desktop\) and email client archives \(MS Outlook and IBM Notes\).

![](../../.gitbook/assets/image%20%28108%29.png)

In the Advanced tab, you can add the additional directory to be protected \(add file extensions and assign a policy by your choice\) by clicking the **Add Include Directory** button. The chosen directory can be deleted by clicking the "x" beside the entry.

![](../../.gitbook/assets/image%20%2899%29.png)

You can also add some directories to be excluded from the policy. Click  

