+++
date = "2015-10-01T17:23:41-04:00"
tags = [
    "node",
    "tooling",
    "development",
    "javascript"
]
categories = [
    "Node",
    "Tooling",
    "Development",
    "JavaScript"
]
title = "Use NVM"

+++

NVM is the Node Version Manager, a bash script you can and should use to manage multiple NodeJS versions.  As a Node developer, you'll invariably find yourself dealing with Node version compatibility issues forcing you to switch versions of Node depending on what you're working on.  It would be nice if Node offered a command like `use 4.1.1`, well NVM does just that.

First install the latest version from [here](https://github.com/creationix/nvm)

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/<LATEST_VERSION/install.sh | bash
```

This will install the `.nvm` file in your user dir and add some lines to your `.bashrc` to source it. If you're seeing some error like `-bash: nvm: command not found` when you try to run the app, chances are you're not sourcing it correctly.

Before we start, let's look at what version of Node we're running:

```
$ node --version
v0.10.22
```

Yikes! Time for an upgrade. What does NVM have available for us?

```
$ nvm list

->       system
node -> stable (-> N/A) (default)
iojs -> N/A (default)
``` 

Ah, well, we haven't installed any new versions yet, so all we have available is `system` which is what we started with.

Let's get a freshie.

```
$ nvm install 4.1.1
######################################################################## 100.0%
WARNING: checksums are currently disabled for node.js v4.0 and later
Now using node v4.1.1 (npm v2.14.4)
```

Ok, I'll Google that warning later, but we have a new version of Node available, but we're not using it yet.

```
$ nvm list
         v4.1.1
->       system
node -> stable (-> v4.1.1) (default)
stable -> 4.1 (-> v4.1.1) (default)
iojs -> N/A (default)

$ node --version
v0.10.22
```


ok so let's use our new version now:

```
$ nvm use 4.1.1
Now using node v4.1.1 (npm v2.14.4)

$ node --version
v4.1.1
```

That easy. Now you can toggle back and forth between Node versions with nary a hassle. Go do it. 


  