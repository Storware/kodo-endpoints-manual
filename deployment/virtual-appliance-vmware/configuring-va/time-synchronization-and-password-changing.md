# Time synchronization \(the OVA with IBM Spectrum Protect server only\)

If the OVA image file has not been used for some time from the moment it was prepared and uploaded to the FTP server, the difference between internal OS time and IBM Spectrum Protect server may appear. In such a case the connection between both servers can be problematic. Additionally, we recommend changing the default password for the IBM Spectrum Protect server user \(the default administration user name is `kodo.va`  to some randomly generated\).

If you are logged in as `kodo` user, go to the /home/kodo directory and run the `kfe_ova_timesynch.sh` script:

```text
$ cd /home/kodo/scripts
$./kfe_ova_timesych.sh
```

The output should be like the one below:

```text
$ ANR0894I Current system has been accepted as valid.
$ ANR2552I Server now enabled for Client access.
```

Go to the [Connecting to the IBM Spectrum Protect server ](connecting-to-the-ibm-spectrum-protect-server.md)chapter to get to know how to configure the KODO for Endpoints server to be able to access the IBM server.

