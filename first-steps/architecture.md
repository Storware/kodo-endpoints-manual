# Architecture

KODO for Endpoints can be installed basically at two configurations: as the gateway and as the bundle. The differences between both configurations are described below. 

**KODO Gateway** is a server installed on a supported operating system platform with preinstalled KODO binaries and MySQL database. An external IBM Spectrum Protect server is required in that configuration to store user data. The administrator has to configure the IBM Spectrum Protect server as the backup engine and connect it to the KODO server. The server is available to download from the Storware FTP server as the OVA image file. 

**KODO Bundle** is a server installed on a supported operating system platform with preinstalled KODO binaries, MySQL database, and preconfigured IBM Spectrum Protect Server. The IBM Spectrum Protect Server was configured with some default retention policies. The server is also available to download from the Storware FTP server as the OVA image file. 

For information on how to download the OVA image file go to the  [Deployment ](../deployment/)chapter. 

Both configurations can be installed on any physical or virtual server that meets server requirements. Go to the [Server requirements](../deployment/kodo-server-configurations.md) chapter to learn more about the server configuration required to deploy the KODO server.

To protect data, the KODO client application must be deployed on each protected Windows-based endpoint. It continuously searches for all files that meet the protection policy and sends them directly to the IBM Spectrum Protect server. This application also listens to the file system when a new file or directory is created, and all changes are tracked and the data is also sent directly to the IBM Spectrum Protect Server.

The architecture of KODO for Endpoints is shown in the following graphic. The core element of the architecture is the KODO server. It's the central point of management. It provides administrative web UI, APIs and is also a central repository of metadata. The metadata is stored in the MySQL database.  

The data itself and information about protected files are sent directly to the IBM Spectrum Protect server. KODO server leverages Spectrum Protect API to connect to the server. Thanks to the LDAP server integration users can be authorized to use their domain credentials when connecting from the KODO client console on endpoints.  

![](../.gitbook/assets/image%20%287%29.png)

Go to the [Licensing ](licensing.md)chapter to learn more about KODO licensing model.

