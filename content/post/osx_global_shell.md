+++
date = "2015-06-02T09:45:42-04:00"
title = "Make a shell script into a global command on OSX"
tags = [
    "bash",    
    "osx",
    "environment",
    "development"
]
categories = [
    "OSX",
    "Bash",
    "Development"
]
menu = "main"
+++


### This example will open a document passed in as param in TextMate.  Obviously, you can use any app you like.

#### 1 Create your script in /usr/local/bin on OSX, it will automatically be added to your $PATH

```sh
/usr/local/bin/tm.sh
```

#### 2 Make the script executable

```sh
chmod +x /usr/local/bin/tm.sh
```

#### 3 Create a symbolic link, so you can skip the .sh suffix

```sh
ln -s /usr/local/bin/tm.sh /usr/local/bin/tm
```

#### 4 Use for increased excellence

```sh
tm coolfile.txt
```

Here's tm.sh

```sh
#!/bin/sh
if [ -z $1 ];
then
  echo 'specify a file to open with TextMate'
  else
  open -a TextMate $1
fi
```
