+++
title = "Kill it"
date = "2017-08-07T12:38:33-04:00"
tags = [
    "bash",
    "Node"
]
categories = [
    "Bash",
    "Node"
]
menu = "main"
+++

You ever get this one?

```sh
{ Error: listen EADDRINUSE 0.0.0.0:8080
    at Object.exports._errnoException (util.js:1036:11)
    at exports._exceptionWithHostPort (util.js:1059:20)
    at Server._listen2 (net.js:1252:14)
    at listen (net.js:1288:10)
    at net.js:1398:9
    at _combinedTickCallback (internal/process/next_tick.js:77:11)
    at process._tickCallback (internal/process/next_tick.js:98:9)
  code: ‘EADDRINUSE’,
  errno: ‘EADDRINUSE’,
  syscall: ‘listen’,
  address: ‘0.0.0.0’,
  port: 8080 }
```
  Or something like it?
  
  Here's a one liner to kill that process.
  

  ```sh
  kill -9 `lsof -ti tcp:8080`
  ```
  
  This gets you the process ID of the application listening on port 8080 and passes it as a parameter to `kill`.  The `-9` flag indicates that the process should be terminated immediately `SIGKILL`.  You can read more about that [here](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGKILL).
  
  
  
  
![kill it](http://i.imgur.com/4iqdTUt.jpg)  