# Architecture

KODO for Endpoints can be installed basically at two configurations: as the gateway and as the bundle. The differences between both configurations are described below. 

**KODO Gateway** is a server installed on supported operating system platform with preinstalled KODO binaries. An external IBM Spectrum Protect server is required in that configuration to store user data. The administrator has to configure the IBM Spectrum Protect server as the backup engine and connect it to KODO server. The server is available to download from the Storware FTP server as the OVA image file. 

For information how to dowload go to the  Deployment chapter. 

**KODO Bundle** is a server  installed on supported operating system platformwith preinstalled KODO binaries and preconfigured IBM Spectrum Protect Server. The IBM Spectrum Protect Server was configured with some default retention policies. 

Both configurations can be installed on any physical or virtual server that meets platform requirements.

On every protected Window-based endpoint KODO for Endpoints client application has to be installed to search for all files that meet the protection policy and send them directly to the IBM Spectrum Protect Server.

The architecture of KODO for Endpoints is shown in the following graphic. The core element of the architecture is the KODO server. It's the central point of management, provides administrative web UI, APIs and is also a central repository of metadata. The metadata is stored in the MySQL database.  

The data itself and information about protected files are sent directly to the IBM Spectrum Protect server. KODO server leverages Spectrum Protect API to connect to the server. Thanks to the LDAP server integration users can be authorized to use their domain credentials when connecting from the KODO client console on endpoints.  

![](../.gitbook/assets/image%20%287%29.png)

Go to the [Licensing ](licensing.md)chapter to learn about KODO licensing model.

