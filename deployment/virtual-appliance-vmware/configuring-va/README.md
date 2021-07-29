# Configuring VA

After the KODO for Endpoints server is deployed and powered on, you can log in to the system and set up network configuration.

{% hint style="warning" %}
Do not change the hostname of the kodo server virtual machine. Changing hostname may lead to system damage. If you need to change the hostname please contact Storware technical support.
{% endhint %}

There is a dedicated user `kodo` to log to KODO server operating system. Logging as the `root` user is not allowed. 

Use the credentials listed below to log in to the system:

> **Login:** kodo  
> **Password:** Zt3edWny

{% hint style="info" %}
**Note**: For security reasons, please change your password after logging in for the first time!
{% endhint %}

Use `passwd` command to change password:

```text
$ passwd
```

Type old password and new password two times:

```text
Changing password for kodo.
Old Password:
New Password:
Retype New Password:
```

The next step is to configure the network connection. The default configuration will try to assign an IP address from a local DHCP server if it exists in a local network. 

Use the `ip a`  command to check assigned IP address to the virtual machine on the interface **ens160**.

```text
# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens160: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:0c:29:12:c8:31 brd ff:ff:ff:ff:ff:ff
    inet 10.40.1.102/22 brd 10.40.3.255 scope global noprefixroute dynamic ens160
       valid_lft 16205sec preferred_lft 16205sec
    inet6 fe80::28b1:17f9:a478:1e05/64 scope link tentative noprefixroute dadfailed
       valid_lft forever preferred_lft forever
    inet6 fe80::2875:6af9:ceed:629a/64 scope link tentative noprefixroute dadfailed
       valid_lft forever preferred_lft forever
    inet6 fe80::cc9:f251:a95:d65b/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
```

If you'd like to change it to the static one, you have to edit the network configuration file. 

Use `sudo` command to run a shell with `root` privileges:

```text
$ sudo -s
```

When asked for a password use password for `kodo` user.

Edit network configuration file e.g. using `vi` editor:

```text
# vi /etc/sysconfig/network-scripts/ifcfg-ens160
```

To set up static IP address change:

```text
BOOTPROTO=dhcp
```

to

```text
BOOTPROTO=static
```

In the next step, add the following entries to the file:

* IPADDR=YOUR\_IP\_ADDRESS
* NETMASK=YOUR\_NETMASK
* GATEWAY=YOUR\_GATEWAY

and change them accordingly to your requirements.

**IPADDR** - IP address of the KODO Server  
**NETMASK** - the netmask value of your network  
**GATEWAY** - the gateway value of your network

Sample configuration file:

```text
TYPE=Ethernet
BOOTPROTO=static
IPADDR=192.168.1.31
NETMASK=255.255.255.0
GATEWAY=192.168.1.1
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=no
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_PEERDNS=yes
IPV6_PEERROUTES=yes
IPV6_FAILURE_FATAL=no
NAME=eth0
DEVICE=ens192
ONBOOT=yes
```

Save the file and exit it by pressing the `ESC`, then `:x!` and then `Enter` key.

The final step is to restart the network configuration. To do this use the command:

```text
# service network restart
```

Now you should be able to log in to your KODO system using a web browser and IP address that you configured in the previous steps. Open a  web browser and enter the address:

```text
https://ip_address:8181
```

KODO login page should be opened.

![](../../../.gitbook/assets/image%20%286%29.png)

If there are no errors on the website, the KODO server is ready to be configured. If you've deployed the KODO for Endpoints Bundle server, go to the [Time synchronization](time-synchronization-and-password-changing.md) section to perform the task for time synchronization between IBM Spectrum Protect server and OS.

{% hint style="warning" %}
KODO for Endpoints server has no license uploaded. Please contact [Storware sales team](mailto:sales@storware.eu) to get a trial license.  
{% endhint %}

