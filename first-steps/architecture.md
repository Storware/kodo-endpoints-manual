# Architecture

KODO for Endpoints can be installed basically in two configurations: as the gateway and as the bundle. The differences between both configurations are described below. 

**KODO Gateway** is a server installed on CentoOS 7 operation system platform with preinstalled KODO binaries. In that configuration, an administrator has to add an external IBM Spectrum Protect server and configure it as the backup engine. The server is availalable to download from Storware FTP server as the OVA image file.  

**KODO Bundle** is a server with KODO binaries installed and preconfigured IBM Spectrum Protect Server. The IBM Spectrum Protect Server was configured with some default retention policies. 

Both configurations can be installed on any physical or virtual server that meets platform requirements. 

The architecture of KODO for Endpoints is shown in the following graphic. The core element of the architecture is KODO server. It's the central point of management, provides administrative Web UI, APIs and is also a central repository of metadata. The metadata is stored in MySQL database.  

The data itself and information about protected files are sent directly to IBM Spectrum Protect server. KODO server leverages Spectrum Protect API to connect to the server. Thanks to the LDAP server integration users can be authorized using their domain credentilals when connecting from KODO client console on endpoints.  





![](../.gitbook/assets/image%20%287%29.png)

Go to the [Licensing ](licensing.md)chapter to learn about KODO licensing model.

