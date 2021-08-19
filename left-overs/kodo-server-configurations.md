# Server deployment options

KODO for Endpoints server can be installed and configured in two options:

* KODO for Endpoints Gateway \(KODO server without IBM Spectrum Protect server\)
* KODO for Endpoints Bundle \(KODO server with IBM Spectrum Protect server included\)

Both options can be deployed as a VMware virtual appliance to the VMware environment, but they can be also configured on a dedicated physical or virtual server.

## KODO for Endpoints Gateway 

KODO for Endpoints Gateway consists of an operating system platform and KODO server binaries. After server deployment, the administrator has to configure access to the external IBM Spectrum Protect server. If you 

## KODO for Endpoints Bundle

KODO for Endpoints Bundle consists of operating system platform, KODO server binaries, and preconfigured IBM Spectrum Protect server with some predefined retention policies. 

Go to the [Planning](../planning/) chapter to learn about KODO server components, server requirements, client application Support Matrix, and sizing guide.

KODO for Endpoints solution consists of the following components:

* KODO for Endpoints server
* KODO for Endpoints client application

KODO for Endpoints server can be deployed in the following options:

* KODO for Endpoints Gateway \(as a virtual or physical server, an external IBM Spectrum Protect server is required\)
* KODO for Endpoints Bundle \(as a virtual or physical server, the IBM Spectrum Protect server is included and preconfigured\)

Go to the [KODO server requirements](../planning/platform-requirements.md) to find out what server specification have to me meet to deploy KODO server successfuly .



You can deploy KODO for Endpoints server by choosing one of the following installation scenarios:

* KODO for Endpoints Gateway \(an external IBM Spectrum Protect server is required\)
* KODO for Endpoints Bundle \(IBM Spectrum Protect server is included and preconfigured\)



Both, KOOD for Endpoints Gateway and KODO for Endpoints Bundle are available to download as virtual appliances. 

Go to the [Virtual Appliance \(VMware\)](../deployment/virtual-appliance-vmware/) chapter to find out how to download OVA image files and deploy KODO appliances.

Optionally, If you are familiar with the IBM Spectrum Protect server and you have one to use as a data repository, you can install KODO for Endpoints server on any dedicated server. In that case,  go to the [RPM packages installation](../deployment/installation-with-rpm-packages.md) chapter to get to know how to configure the KODO server using the gateway configuration option. 

Go to the [Virtual Appliance \(VMware\) ](../deployment/virtual-appliance-vmware/)to find out how to download, install and configure KODO for Endpoints server as a virtual appliance.



There are two types of people: those who are doing backups, and those who will be doing them. But just **doing** backups is not everything. To avoid unnecessary surprises the best strategy is to **plan** your backup environment/procedure **before implementing** it. In this section, we've collected guides that you may find useful as you think about your KODO for Endpoints implementation.

  

