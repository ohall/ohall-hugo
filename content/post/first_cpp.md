+++
date = "2013-03-02T10:17:40-04:00"
title = "Writing your first C++ program on a Mac"
tags = [
    "osx",
    "c++",
    "development"
]
categories = [
    "OSX",
    "C++",
    "Development"
]
+++

A friend of mine recently started his first computer science class. His entire class in working on Windows machines and using Visual Studio.  He wants to use his Mac.  I know how frustrating setting up development environment for the first time can be.  He're how I advised him to get started and write is first code.

### You need two things to write programs in C++.

1. You need a compiler.  A compiler is an application that takes the code you write in a human readable language ( C++ in this case ) and converts it into machine code so it can run.  If you're a mac user and you want to write any C based code, you'll need to install Xcode. Xcode comes with a C++ complier called g++, which is what you'll end up using one way or another even if you don't use the Xcode editor.

2. You'll need a text editor.  Basically that means any application that lets you write plain text and save it to your machine.  Xcode, CodeBlocks, Visual Studio and Eclipse are all called IDEs or integrated development environments. The are just big text editors with tons of bells and whistles.

### Installing g++

 Follow [these instructions](http://www.edparrish.net/common/macgpp.php) to make sure you have Xcode and g++ on your Mac.  You can follow Mr. Parrish's instructions for writing your first program, but I think mine are even simpler.
 
### Writing your first code:

#### Start with the simplest mac text editor TextEdit.  It should be in your Applications folder.

#### 1. Type in this code:

```
#include <iostream>

int main()
{ 
  std::cout << "Hello world!" << std::endl; 
}
```

#### 2. Save the file to your Desktop as a plain text document with the name helloworld.cpp  the .cpp extension lets the compiler know its C++ code.

<img src="/images/cpp1.png"/>


### Compiling and running your program

First, open a terminal window.  You'll find this in Applications/Utilities/Terminal. (yours will be different colors than mine)

<img src="/images/cpp2.png"/>

In the terminal window type:

```
cd ~/Desktop
```

This is how you navigate from your home directory ( abbreviated `~` ) to the directory called `Desktop`.

Then type:

```
g++ helloworld.cpp -o hw
```

This will take your C++ code you saved to the desktop and compile it into an application called `hw` which is save to the desktop.  You can see it there if you look.

Now type:

```
./hw
```

This will tell your Mac to run the program.

If the terminal says: `Hello World!`  then __you did it!__  
You can write any C++ program in this way.

<img src="/images/cpp3.png"/>

If you want a nice book on getting started with C (the core of C++) I'd recommend [Head First C](http://amzn.to/1J7gJ7M).

Programming is fun and satisfying, but you will continually have to break through periods of confusion and frustration.  Stick with it, it's worth the effort.  Good luck!
