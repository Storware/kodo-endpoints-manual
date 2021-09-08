# "All-in-One" Installation

Kodo for Endpoints can be easily installed on a single box quickly. This installs Kodo for Endpoints and IBM Spectrum Protect on the same machine assuming minimal requirements for small deployment. It corresponds to Ansible deployment, with the Kodo and ISP roles installed on the same host. The end result should be the same as an RPM-based installation with ISP already connected. 

License still needs to be uploaded after installation. 

Here are just a few steps that need to be completed:

1. Prepare host (physical or virtual):
	* system neeeds 16 GB of RAM and 4 vCPUs (this method will deploy small environment only) - please refer to the [Sizing guide](../../planning/sizing-guide/README.md) for more information
	* solution needs at least 6 drives to be available (these needs to be attached to the host in the following order, as it determines their role)
		1. operating system and Kodo Server (100 GB)
		1. ISP database (100 GB)
		1. ISP active log (35 GB)
		1. ISP archive log (100 GB)
		1. database backups (100 GB)
		1. backup data (1 TB+ - more than 1 drive are supported with Ansible-based installation or when you provide YAML file with overridden parameters)
1. Install CentOS or RHEL 8 (optionally you can use version 7) minimal - make sure to have
   * RHEL 8 requires an active subscription
	* Internet connectivity - these are required for package installaltion
	* FQDN and hostname configured in the OS - which is also resolvable in your DNS
1. 	Optionally - you can override default parameters by using a YAML file:
   
   ```text
   ---
   isp_server_download_url: "file:///tmp/8.1.12.000-IBM-SPSRV-Linuxx86_64.bin"
   isp_client_download_url: "file:///tmp/8.1.12.0-TIV-TSMBAC-LinuxX86.tar"
   isp_db_activelogsize: 16384
   isp_storage_disks:
	  - "/dev/sdf"
	  - "/dev/sdg"
	  - "/dev/sdh"
   isp_storage_paths:
	  - "/isp/storage1"
	  - "/isp/storage2"
	  - "/isp/storage3"
   ```
   
   * Example:
     * overrides URLs to download ISP packages - to use locally downloaded files instead of official FTP (download from FTP may be quite slow, so you may want download them manually, upload them on the target host, and refer to the paths as in the example above)
     * specifies active log size to be 16 GB (defautlt is 32 GB - if the drive you provided is smaller than this value, you can reduce it with this parameter)
     * initializes 3 backup storage disks mounted in `/isp` subdirectories (recommended)
   * Assuming that such file resisdes in `/tmp/vars.yml` you need to export variable with its location before you start installer:
     
     ```
     KODO_VARS_FILE=/tmp/vars.yml 
     ``` 
1. Copy-and-paste this command and press ENTER:

     ```
     bash < <(curl -s http://repo.storware.eu/kodo-endpoints/kodo-endpoints-local-install.sh)
     ```

1. Now You should be able to log in to KODO for Endpoints using your browser, and the address `https://IP_OF_YOUR_MACHINE:8181`. Use global admin account `kodoadmin` with password `k0do@dmin`. Proceed with the [Initial configuration](initial-configuration.md) to upload license, and deploy agent on your endpoints. 

