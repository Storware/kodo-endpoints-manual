# Time synchronization and password changing

If the OVA image file has not being used for some time from the moment it was prepared and uploaded to the ftp server, the difference between internal OS time and IBM Spectrum Protect server may appear. In such a case the connection between both servar can be problematic. Additionally, we recommend to change the default password for the IBM Spectrum Protect server user \(the default administation user name is `kodo.va`  to some randomly genarated\).



If you are logged in as `kodo` user, go to the /home/kodo directory and run the `kfe_`_`ova`_`_init.sh` script:

```text
$ cd /home/kodo/scripts
$./kfe_ova_init.sh
```

Tteh output shoud be like the one below:

```text
$ ANR0894I Current system has been accepted as valid.
$ ANR2552I Server now enabled for Client access.
$ ANR2071I Administrator KODO.VA updated.
$ New password generated! Check /opt/storware/kodo-server/api-core/logs/tsm_password.txt


```

The new password is needed to connect IBM Spectrum Protect server to the KODO for Endpoints server.

{% hint style="warning" %}
Please make a copy of that file or write down the new password and keep it in some save place.
{% endhint %}

 

