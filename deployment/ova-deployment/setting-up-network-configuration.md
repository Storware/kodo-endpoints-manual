# Setting up the network configuration

The next step is to configure the network connection. The default configuration will try to assign an IP address from local DHCP server if it exits in a local network. 

Use the `ip a`  command to check assegned IP address to the virtual machine on the interface **ens160**.

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

![](../../.gitbook/assets/image%20%286%29.png)

If there are no errors on the website, the KODO server is ready to be configured. Go to the [Time synchronization and password change](time-synchronization-and-password-changing.md) chapter to perform a task for time synchronization and password change.

{% hint style="warning" %}
KODO for Endpoints server has no license uploaded. Please contact [Storware sales team](mailto:sales@storware.eu) to get a trial license.  
{% endhint %}

