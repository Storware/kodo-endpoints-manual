# Connecting to the IBM Spectrum  Protect server

KODO for Endpoints server is using IBM Spectrum Protect server as a backup engine to store data from the protected endpoints. It's required to configure it in an appropriate way.

In the first step, log in to  the KODO Portal as the `kodoadmin` user and go to the Settings menu.

Next, switch to the IBM Spectrum Protect tab. Check, if the proper port numbers are set:

* **Port** - set the number at 1502 
* **Administrative Port** - set the number at 1503

Do not change the **Nodename** name \(the **kodo.va** is the default one\). Click the **Save** button.

The **Server Connection Status** should be changed to **Connected** \(it may take a while\).  If the status is **Not connected**, please refresh the web browser site.

![](../../../.gitbook/assets/image%20%2814%29.png)

If you've obtained a trial license from the Storware sales team or purchased it, go to the License tab and upload it.

If the license is uploaded, go to the [Administration](../../../configuration/) chapter to learn how to start KODO for Endpoint server configuration. 



