+++
date = "2015-10-05T15:15:15-04:00"
tags = [
	"devops",
	"linux"
]
categories = [
	"DevOps",
	"Linux"
]
title = "How to check if a port is open on a remote server using netcat"

+++



Assuming you have ssh access to the remote server you can check the status of a give port with netcat (`nc`).

In a terminal window logged into the server use this command with the `-l` flag to listen and the port you want to test (by listening on).

```
$ nc -l 443
```

This will leave you with a prompt, don't do anything yet.

In another terminal on your local machine. Call `nc` again, this time with the IP of your remote server and the port to test as params. If nothing is listening on that port, nothing will happen. If it is closed, it will timeout. (But we KNOW netcat is listening!)

```
nc XXX.XX.XX.XXX 443
```
Go back to the terminal window on the server and type something in the prompt and hit enter:
```
$ nc -l 443
foo
```
on the client machine, you should see this come though

```
nc XXX.XX.XX.XXX 443
foo
```
You can type messages both ways, but you know know you have an open port.

Cool right? ...whatever, I think it's cool.