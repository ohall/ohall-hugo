+++
date = "2016-07-25T11:53:46-04:00"
draft = true
tags = [
    "bash",
    "development"
]
categories = [
    "Development",
    "Tooling"
]
menu = "main"
title = "Getting Started 0: The Terminal"

+++
So you're learning to code?  There first think you should get familiar with is the Terminal and the command line. Let's discuss some basics.

## What is it?
I'll keep my comments confined to OS X and Linux, since those are the environments I'm familiar with.  The Terminal is an application that provides you a window through which to enter commands into the Unix [shell](https://en.wikipedia.org/wiki/Unix_shell) of your choice, most systems default to [BASH](https://www.techopedia.com/definition/3520/bourne-again-shell-bash).  

On OS X you can find the Terminal App in 
`Applications -> Utilities -> Terminal.app` 

on Linux
`Applications -> Terminal`

<img src="/images/term.png"/>


## Why bother?
You might be thinking: "This seems like a lot of work. Why can't I just doing everything from the Desktop."

Sure. You could, but you'll be missing out on incredibly powerful tools and scripting capabilities.  As your programming projects become more complex, you'll need more tools. Local servers, file manipulation, automation, scripting, NodeJS, Git and a galaxy of other single purpose command line applications that you'll weave into a efficient development environment.  You'll also eventually have to deploy your work on a server somewhere and likely the only interface available to you will be the command line.

At first it will take you more time to do things in the terminal and you'll make mistakes, but think of it as and investment that will pay enormous dividends in the future.  Also, if you're planning to work as a developer or in any other technical role, you'll be expected to know your way around.       

## Basic commands and tools
Let's look at a few commands that may shed some light on what may initially feel like a very dark room.  

Most terminal applications take a variety of flags and arguments. We'll just cover the simple user cases here, but you can see everything that's possible by using the `man` (manual) command. When in doubt, RTFM.

```sh
$ man pwd
```

### Ctrl-C and Ctrl-Z
Many times per da, you will get stuck or want to exit a program you've started on the command line. These two key combos will do it.  You'll learn the difference as you go, but for now try either or both to get out of a running process and back to the command prompt.
 
`Ctrl-C` cancels or kills a job. Technically it causes an interrupt signal to be sent to the program telling it to abort what it is doing and exit immediately.

`Ctrl-Z` "puts a job on hold and returns you to the prompt, but does not kill the job.

### pwd
Print Working Directory. Basically asks where am I now?

```sh
$ pwd
/Users/oakley
```
Use this command liberally to see what directory you're working in.

### ls
List file and directory names.  Basically, show me the contents of a directory.

```sh
$ ls
Applications    Dropbox    Pictures    Sites
Desktop         Library    Public      Documents               
Movies          Downloads  Music                   
```

### mkdir
Make a new directory.

```
$ mkdir test-directory

$ ls
test-directory
```

### cd
Change directory. Specify the directory you want to work in

```
$ cd test-directory

$ pwd
/Users/oakley/test/test-directory
```

### touch
`touch` is the equivalent of creating or opening a file and saving it without any actual changes.  It's often used to create new files.

```
$ touch file.txt

$ ls
file.txt       test-directory
```

### rm
Remove a file. Like FOREVER. Not put it in the trash, it's gone.

```
$ rm file.txt

$ ls
test-directory
```

### cp
Copy a file to another location.
In this example, we'll recreate `file.txt`, use `cp` to copy it into `test-directory`, then use `ls` to see that `file.txt` has been copied there.

```
$ touch file.txt 
$ cp file.txt test-directory
$ ls test-directory 
file.txt
```

### mv
Move a file. Same as `cp`, but removes the original.

```
$ touch foo.txt

$ ls
file.txt    foo.txt    test-directory

$ mv foo.txt test-directory

$ ls
file.txt   test-directory

$ ls test-directory
file.txt foo.txt

```

### cat
Display a file's contents on screen or concatenate files.

```
$ cat file.txt
Some text here...
```
### pipes
Pipes let you pass the output of one command into another command as an argument.  Let's say you want your computer to say the contents of a directory out loud.  You could pipe the output of `ls` to `say` or `espeak` on linux.

```
ls | say
```

Try it!

### text editors

## Tools to get started

## Further reading
