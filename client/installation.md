Download an installation package as described in [__Deployment__](../management/client-deployment/README.md) section.


{% hint style="info" %}
If there was previous installation of KODO for Enpoints,
ANY content of C:\ProgramData\Storware\Kodo\ should be removed before installation!
{% endhint %}



__Domain user__


In order to use the application, the user must be logged in, activated and perform the first full backup. In order to do this, run the application at the first time, and fullfill following configuration fields: "__Server__" enter the server address of your organization. In the field "__Username__" enter the user name as "_domain\username_". In the "__Password__" enter the password, which is used as the password for e-mail and click "_Log in_". If the server at that address does not start or the address is incorrect, the user will see a message.


![](../.gitbook/assets/kodologin.png)

__Standalone user__



The user will be asked to enter the following information:
1. __Server__ - KODO for Endpoint server address
2. __Username__ - Client Username
3. __Password__ - Password 


After fulfilling these fields just click __Log in__ button.

![](../.gitbook/assets/kodologinstandalone.png)

{% hint style="info" %}
After installation and login the process of securing the files in the selected locations will begin automatically according to assigned policy.
{% endhint %}