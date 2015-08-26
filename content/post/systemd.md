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

systemd is an init system that most linux distributions are standardizing on and a crucial tool for any system admin.

In Unix and Linux, background processes are called daemons.  systemd calls these "units".  You can see what units you have on your machine you can use the [`systemctl`]() command. Here we'll pass the parameter `list-units`.

```
$ systemctl list-units
```

You'll see some stuff like this