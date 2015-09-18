+++
date = "2015-08-26T07:51:50-04:00"
draft = true
tags = [
    "linux",
    "ops",
    "devops"
]
categories = [
    "Operations",
    "DevOps"
]

title = "systemd"

+++
## Intro
systemd is an init system that most linux distributions are standardizing on and a crucial tool for any system admin or devops engineer.

In Unix and Linux, background processes are called daemons.  systemd provides a syntax for creating objects that can be managed by the daemons in the form of __units__.  

You can see what units you have on a machine with the [`systemctl`](https://wiki.archlinux.org/index.php/Systemd#Basic_systemctl_usage) command. Here we'll pass the parameter `list-units`.  Which will list all the units.

```
$ systemctl list-units
```

You'll see some stuff like this describing your available units:

```
UNIT                                  LOAD   ACTIVE SUB       DESCRIPTION
proc-sys-fs-binfmt_misc.automount     loaded active waiting   Arbitrary sys-d
sys-devices-...dports-vport1p1.device loaded active plugged   /sys/devices/pci
sys-devices-...-block-vda-vda1.device loaded active plugged   /sys/devices/pci
app.mount                             loaded active mounted   /app
dev-mqueue.mount                      loaded active mounted   POSIX Message proc-fs-nfsd.mount                    loaded active mounted   RPC Pipe File sys
sys-kernel-debug.mount                loaded active mounted   Debug File System
var-lib-nfs-rpc_pipefs.mount          loaded active mounted   RPC Pipe File 
...
```

## Basic usage
### Getting system state
#### List currently running units:

```
$ systemctl
```
__or:__

```
$ systemctl list-units
```
#### List failed units:

```
$ systemctl --failed
```
__Unit files can be found in__ `/usr/lib/systemd/system/` and `/etc/systemd/system/`. 

#### List installed unit files with:

```
$ systemctl list-unit-files
```

## Working with units
Basic unit commands are:

##### Start a unit immediately:
```
$ systemctl start unit
```
##### Stop a unit immediately:
```
$ systemctl stop unit
```
##### Restart a unit:
```
$ systemctl restart unit
```
##### Ask a unit to reload its configuration:
```
$ systemctl reload unit
```
##### Show the status of a unit, including whether it is running or not:
```
$ systemctl status unit
```

[Other commands can be found here](https://wiki.archlinux.org/index.php/Systemd#Basic_systemctl_usage)