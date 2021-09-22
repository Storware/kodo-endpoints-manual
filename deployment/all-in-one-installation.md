# "All-in-One" Installation

KODO fo Endpoints server can be installed on a physical or virtual machine in the "All-in-one" configuration. To do this, the customized script can be executed. It configures server all required server resources \(dedicated disk partitions\), installs IBM Spectrum Protect binaries and KODO for Endpoints server bibaries and the service. 

The installation script can be found at the address [http://repo.storwa.eu/kodo-endpoints/kodo-endpoints-local-install.sh](http://10.40.0.253/kodo-endpoints/kodo-endpoints-local-install.sh).

Before you start the installation process please do the following tasks:

1. Install and configure a server according to the requirements of your environment \(see the [Sizing Guide](../planning/sizing-guide/) section\).
2. Log in as **root** user over **SSH** protocol to the machine you want to install KODO for Endpoint server on.
3. Run `lsblk` command to check the system name for the disk you will use as a storage destination. 
4. In this example, disk **sdb, sdc, sdd, sde, sdf** were added to the system platform.

   ```text
   [root@centos8 mapper]# lsblk
   NAME                   MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
   sda                      8:0    0   50G  0 disk
   ├─sda1                   8:1    0  600M  0 part /boot/efi
   ├─sda2                   8:2    0    1G  0 part /boot
   ├─sda3                   8:3    0 14.4G  0 part
   │ ├─vg_system-lv--root 253:0    0 46.8G  0 lvm  /
   │ └─vg_system-lv_swap  253:1    0  1.6G  0 lvm  [SWAP]
   └─sda4                   8:4    0   34G  0 part
     └─vg_system-lv--root 253:0    0 46.8G  0 lvm  /
   sdb                      8:16   0  100G  0 disk
   sdc                      8:32   0   35G  0 disk 
   sdd                      8:48   0   70G  0 disk 
   sde                      8:64   0   70G  0 disk 
   sdf                      8:80   0    1T  0 disk 
   ```

5. Prior to installation, make sure you've got access to **repo.storware.eu** site.
6. Now the system platform is ready to deploy KODO for Endpoints server. To start server installation, copy and paste this command to the system console and press ENTER:

   ```text
   # bash < <(curl -s http://repo.storware.eu/kodo-endpoints/kodo-endpoints-local-install.sh)
   ```

7. The installation process may take up to 30 minutes, but it depends on your system performance.
8. After the installation process is finished, you can check the KODO server service status by using the following command:

   ```text
   [root@centos8]# systemctl status kodo-for-endpoints
   ● kodo-for-endpoints.service - Storware Kodo for Endpoints
      Loaded: loaded (/usr/lib/systemd/system/kodo-for-endpoints.service; enabled; vendor preset: disabled)
      Active: active (running) since Wed 2021-09-22 13:05:17 CEST; 3h 18min ago
       Tasks: 156 (limit: 100655)
      Memory: 3.1G
      CGroup: /system.slice/kodo-for-endpoints.service
              └─150221 java -XX:+DisableExplicitGC -XX:+UseG1GC -XX:+UseStringDeduplication -XX:MaxGCPauseMillis=500 -Xmx2g -Xms2g -jar ../lib/kodo-server-api.jar --systemproperties ../config/payara.properties

   Sep 22 13:04:34 centos8 systemd[1]: Starting Storware Kodo for Endpoints...
   Sep 22 13:05:17 centos8 start.sh[150199]: Starting API (pid:150221)..........................................................................................................................................................................................................................>
   Sep 22 13:05:17 centos8 start.sh[150199]: API successfully started.
   Sep 22 13:05:17 centos8 systemd[1]: Started Storware Kodo for Endpoints.
   ```

9. You can also use the command below to check version of the installed KODO for Cloud server:

   ```text
   [root@centos8 /]# curl -k https://localhost:8181/api/version
   {"value":"4.1.5"}
   ```

10. If the KODO server is up and running, you should be able to log in to KODO for Endpoints using your browser, and the address `https://IP_OF_YOUR_MACHINE:8181`

{% hint style="info" %}
Kodo for Endpoints server credentials are presented in chapter  [Administration levels](administration-levels-1.md)
{% endhint %}

