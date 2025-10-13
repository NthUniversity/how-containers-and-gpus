# Basic commands to navigate Ubuntu #

## General ##

`lsb_release -a`
* 'Linux Standard Base RELEASE'

`sudo <command>`
* 'Super User DO'

`export <var_name>=<var_value>`
* sets environment variable
* `echo $var_name` prints environment variable value


## Files, Directories & Storage ##

`df -h`
* 'Disk Free'
* -k lists in kilobytes
* -m lists in megabytes

`ls`
* 'LiSt'
* -l lists details

`cd <dir_name>`
* 'Change Directory'

## Networking

`ip a`
* 'IP Address'
```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 52:54:00:c5:65:f6 brd ff:ff:ff:ff:ff:ff
    altname enp3s0
    inet 10.106.5.63/20 metric 100 brd 10.106.15.255 scope global dynamic eth0
       valid_lft 24087sec preferred_lft 24087sec
    inet6 fe80::5054:ff:fec5:65f6/64 scope link
       valid_lft forever preferred_lft forever
```

## Devices ##

`lsblock`
* 'LiSt BLOCK' (disk devices)

`lspci`
* 'LiSt PCI' (peripherals)
* `lspci | grep -i nvidia`

## Packages and Software ##

`apt-get` or `apt`
* 'Applaication Package Tool'
* `sudo apt update` updates catalog of available packages
* `sudo apt upgrade -y` updates all applicable packages
* `sudo apt insatll <package>` installs package
