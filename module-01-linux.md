# Basic commands to navigate Ubuntu #

## General ##

`lsb_release -a`
* 'Linux Standard Base RELEASE'

`sudo <command>`
* 'Super User DO'


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
