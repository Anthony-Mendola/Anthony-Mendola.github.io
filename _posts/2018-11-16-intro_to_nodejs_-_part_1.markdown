---
layout: post
title:      "Intro to Nodejs - Part 1"
date:       2018-11-16 21:30:59 +0000
permalink:  intro_to_nodejs_-_part_1
---


This is a brief introduction to gain an overall understanding of what exactly Nodejs is and what its used for.

**What is Nodejs?**

Nodejs is an environment to run JavaScript outside of a browser. It's built on Google Chrome's V8 engine. Before node we used JavaScript to build applications that only run inside a browser. Every browser has a JavaScript engine that converts JavaScript to machine code. MS Explorer uses Chakra, FireFox uses SpiderMonkey, and Chrome uses V8. Up until 2009, JavaScript could only be executed in the browser. Ryan Dahl invented Nodejs by embedding Chrome's V8 into a C++ program called Node. 

**What's so good about Nodejs?**

Node is fast and highly scalable. To give you an idea of how powerful Nodejs can be. PayPal was able to rebuild their system with Node twice as fast with fewer people using 33% fewer lines of code. The amount of files were cut in half and they achieved a 35% faster response time. 

Node uses JavaScript and is a great choice for frontend developer's who are looking to become a Full Stack and get into backend. Using JavaScript for both frontend and backend leads to a cleaner more consistent codebase.

Node also has a large ecosystem of open-source libraries. This is a huge plus because any feature or build tool you want to add is completely free.

**Differences between Nodejs and browser JS**

In Node there is no document object but there are other objects like the file system and ability to listen to requests on a given port. Those are not available in a browser. 

*Browser with JavaScript:*

* Build interactive apps for the web
* DOM
* Window
* Fragmentation
* No access to file system
* Async

*Nodejs with JavaScript:*

* Build serverside apps and scripts with 
* No GUI - pure logic and no interface
* No window but has global
* No fragmentation but is versioned
* Required Modules
* Can access file system
* Async
* No browser based APIs

**What can I build with Nodejs?**

Anything you can build with a scripting and server language like Python or Ruby can be build with JavaScript in Nodejs.
This includes things like: 
* Tooling (build, automation)
* APIs (REST, Realtime)
* CDNs
* Shareable Libraries
* Desktop Applications
* IoT

**Modules in Nodejs**

Node uses CommonJs for it's module system. 

*What the heck is a module? *

On a high level, it's just encapsulated code. Modules are functions that inject globals into your code.  Modules are required and there's no way around this. There's no script tags and there's no DOM so it's the only way to share code throughout your application. Another popular module is ESM (ecmascript modules) which allows you to write in ES6. This is used by most node developers but requires transpiling for compatibility. Node is in the process of making ES6 a standard.

All of the code you create in Node are modules. You just have to export it. If you don't export your code it will be unusable. 

*Using Modules*

The Nodejs runtime injects another global, ` require`. This function takes a relative path to the module that you want to consume, and synchronously loads it by returning whatever the target module exported. Always ensure to put a dot before your relative path if it's a module you created in the same repo. 

To export you would do `module.exports =` followed by the name of the function or the function itself that you want to export. 


