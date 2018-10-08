---
layout: post
title:      "Project 4: Javascript"
date:       2018-10-08 19:52:05 +0000
permalink:  project_4_javascript
---


When learning anything new, the farther you get, the more complex it gets. This is no exception. This was the hardest project I’ve done so far, but I’m not surprised. 

When starting this project, I tried to get small things working, to make sure I was doing it correctly. I got a few thing working, but immediately noticed something weird. I had some links, that I “hi-jacked” with JQuery, to do something other than be redirected to another page. And it worked the first time you clicked the link, everything was displaying how I wanted it to. But when I clicked another link, for example the “Home” link, and went back to the link that I “hi-jacked”, it no longer did anything. It’s like it could only render the JQuery request once. The only way to get it to work again was to refresh that page. This was not the functionality that I wanted, and I looked everything online to see if anyone else had this same issue. There were a few things that looked promising, but none of them worked for me. I finally decided to try something else. Instead of using the `<a href>` link tag, I used a simple `<span>` tag to make a line of text to click instead. In this element, I added an `onclick` command that triggered a function I made in my JS file. In this function, I copy and pasted the same code that I had for my `<a href>` link tag. Magically, it worked perfectly. I could click that `<span>` element all day long and it would do what it’s supposed to do. 

Now that I had that problem fixed, I went on to do a little more complicated stuff. The aspect that gave me the most trouble was adding comments. I wanted the user to be able to add a comment with JS so that the page didn’t refresh every time. For some reason, when I used the `.val()` method on the input box for a new comment, it would only work once. I could add a comment, and it would be added to the DOM perfectly, but when I went to edit that comment, it kept the comment the same. Even when I deleted the comment, and tried to add a new comment, it would add the original comment! This made no sense to me, because that comment wasn’t even on the page anymore, how could it be pulling that information still? It turns out, that when I was creating a new comment, it was putting that new comment in as an array element on the JQuery object for the input field. In order to get it working, I had to use `.last().val()` instead of just `.val()` because without the `last()` it was grabbing the first one made each time, thus not updating. Once I figured that out, everything was working how I wanted it to. 

This was definitely a challenging project, but I always learn better when I do things myself, and failing is a part of that. When you fail, you learn why things failed, and more importantly, you learn how to fix them.
