+++
date = "2015-08-17T06:03:19-04:00"
title = "Stop trying to learn a programming language"
tags = [
    "javascript",
    "development"
]
categories = [
    "Development",
    "JavaScript",
]
menu = "main"
+++

I hear this question all the time: 
	
	"Which programming language should I learn?"

My answer is always the same:

	"It doesn't matter. Let the project decide for you."

#### A story
When I first started my journey as a professional software developer, I got hired to work on an application written in a dying language on a platform that would soon be reviled the world over. This project was written in ActionScript 3, using the Flex framework. This was cutting edge stuff at the time, with a bright future, before Steve Jobs and 0 day exploits crapped in the Flash punch bowl. 

The point is, I started learning my craft using a language that I'd probably never see again, __but that never mattered__. What mattered is that I worked with a brilliant team who took time to train me in the craft of programming. I learned the fundamentals of software development and I learned the tools I have used every day since I started that project.

An aspiring programmer fretting about what language to develop in is like a carpenter worrying about what wood to use. It's one of many choices to be made about a project, but it does not define the carpenter's expertise. 

What matters is not the material you work in, but the tools, the craft, and the mindset you develop.

## The tools

### Version control
Understand [version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control). [Git](https://git-scm.com/about) is the most popular at the moment and seems to have a firm hold on the space. Use [GitHub](https://github.com/). [Branch](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell), [tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging), do [pull requests](https://help.github.com/articles/using-pull-requests/), even if they are just against your own code. You can version control any file. Use git for papers, blog posts, any document that you'll want to have a record of changes to.

### Text editor
Pick something and become a power user. I personally feel most at home in an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment), so I spend most of my time writing JavaScript in [Webstorm](https://www.jetbrains.com/webstorm/) and [Sublime Text](http://www.sublimetext.com/). I've created a ton custom templates that autocomplete common code snippets. I know many keyboard shortcuts and tricks to simplify and expedite my workflow. It's the equivalent of sitting in the driver's seat of a car and adjusting the mirrors and familiarizing yourself with the controls. I try to learn a little something new every day. Some devs recommend working without a mouse one day a week. I haven't had the nerve for that one yet. 

### The terminal
This is among the most important skills you'll need as a developer. This will come up over and over and over. Get comfortable navigating the files system in the terminal, running applications, viewing and changing permissions(`chmod`), piping data from one app to another (`|`). Searching for text strings in a file or directory (`grep`).

<img src="/images/so_you_wanna_dev1.png"/>

Eventually, you'll need tools like `ssh`, `scp` and the whole panoply of command line utilities available on the Unix platform. I'm told Windows has stuff like that too.

## The platform

Where is your code going to execute?  How will your users interact with it. For me, right now, that's in the browser an [HTTP API](http://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340). Well, [what is a browser](http://googleblog.blogspot.com/2009/10/what-is-browser.html)? [How does HTTP work](http://www.slashroot.in/httphypertext-transfer-protocol-request-and-response)? What [tools](https://developer.chrome.com/devtools) [are](https://developer.mozilla.org/en-US/docs/Tools) [avaialble](https://developer.apple.com/safari/tools/) to [developers](https://msdn.microsoft.com/en-us/library/dd565628(v=vs.85).aspx)?  

<img src="/images/so_you_wanna_dev2.png"/>

This is your world. These are the rules that will define what you can do and the platform on which you'll be doing it. This is your users whole experience. Before you learn anything about a language, you have to understand the environment in which it will execute. 

## The craft

[Buy this book](http://amzn.to/1hozy0j) and read it more than once. 

Your early code is going to suck. In fact most of your code is going to suck, as will most of the code you will ever read. Nevertheless, you will persevere in the eternal struggle against entropy. You will endeavor to make your code readable and performant and something you are proud to show to others. Embrace simplicity, modularity, decoupling, testing, automation, documentation and all the other [hallmarks of a software craftsman](https://pragprog.com/the-pragmatic-programmer/extracts/tips).

<img src="/images/so_you_wanna_dev3.png"/>

## The mindset

### Check your ego at the door. 
You're going to hear criticism of your bad code, don't shy away from that. Embrace it, learn from it, write it down. Endeavour not to make the same mistake twice. Do not hide your code, seek review and criticism. This is how you will grow. Seek out more senior programmers and read their code. Show gratitude when they take the time to tell you what to fix in yours. 

### Make stuff constantly
Some people can read book to learn how to do things. Not me. I can only learn by doing things badly and then researching, reading and iterating over it. Thus, I must constantly be working on side project to learn how to do anything. __Think of something you want to make and then figure out how to do it one small piece at a time.__ This is the formula.

### Read, read and listen
Read [books](http://stackoverflow.com/questions/1711/what-is-the-single-most-influential-book-every-programmer-should-read), read [blogs](http://blog.codinghorror.com/), read [hacker news](https://news.ycombinator.com/), read [Stack Overflow](http://stackoverflow.com/) read [code](https://github.com/joyent/node/blob/master/lib/_http_server.js), listen to [podcasts](https://devchat.tv/js-jabber/). Perhaps the 300th explanation of a concept will be the one that sinks in. 


## Conclusion
There is so much to do! Why are you fussing about which language to learn? Focus on what you want to create. Become a technologist and a craftsman. Make things! Start right now! You'll learn language syntax as you go, but it will be incidental to learning how to create software holistically and how to make cool things that people will want to use.
 