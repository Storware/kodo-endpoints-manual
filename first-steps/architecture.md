# Architecture

KODO for Endpoints can be installed in two configurations: as the gateway and as the bundle. THe differences between both configurations are described below. 

KODO Gateway is a server installed on Centos 7 operation system platform with installed KODO binaries. In that configration, an administrator has to add an external IBM Spectrum Protect server and configure it as the backup engine. The server is avaialable to download from Storware FTP server as the OVA image file.  

KODO Gateway can be also installed on any physical or virtual server that meets platform requirements. 

KODO Bundle is a server with KODO binaries installed and preconfigured IBM Spectrum Protect Server. The IBM Spectrum Protect Server was configured with some default retention policies. 

The architecture of KODO for Endpoints is shown on the following graphic. The core element of the architecture is KODO server. On the server is also installed MySql database, that stores information about backed up files. 

The metadata about protected files are sent directly to KODO server, and data directly to the IBM Spectrum Protect server. KODO server leverages Spectrum Protect API to connect to the server. Thanks to the LDAP server integration users can be authorized using their domain credentilals when connecting from KODO client console on endpoints.  





![](../.gitbook/assets/image%20%287%29.png)

Go to the [Licensing ](licensing.md)chapter to learn about KODO licensing model.

