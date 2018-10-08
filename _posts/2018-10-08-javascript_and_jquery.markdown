---
layout: post
title:      "Javascript and JQuery"
date:       2018-10-08 18:17:01 +0000
permalink:  javascript_and_jquery
---


This was difficult for me to grasp at first, especially coming straight from Rails. Although Rails a JQuery are similar in a way, at first they seemed like completely different. 

The first thing you need to know about JQuery, is that all we’re basically doing is passing information around. Here are the basic steps of a “get” request with JQuery:

1. There needs to be something that the user can click, or interact with, in order for the “get” request to fire. You can either hi-jack a link, or add a `onclick` method to an element that fires a function in your Javascript file. 
2. You must have the URL that you will be getting information from. If you’re using RESTful routes, it might look something like this: “/posts”. This would be the index page for all the posts. When you are figuring out the correct URL, you can use `rake routes` as a guide. Once you have the correct URL, and you know which function it corresponds to in the controller (in this example it would be "index"), you will need to add functionality to that controller. 
3. In the Posts controller, in the index function, you will need to get any information you need to send back to your JQuery “get” request. In this case, it makes the most sense to get all the posts. You will want to assign that to a variable, such as `@posts`, and then render that as JSON to send back to your JQuery request: `render json: @posts`. Another possible thing to send back is whatever you have in the view file that corresponds to that method. For example, you might have a form, or a list of authors in there, that you will be rendering back to the “get” request (`render :layout => false`). 
4. If you’ve sent back the `@posts` object, it will be sent over as a JSON object. Now you can do whatever you need to do back in your Javascript file, such as iterating over each post, and putting the title and content in the DOM. 
5. To put the information into the DOM, you will need to make a place holder for the information that you can access, and add to, such as a `<div>` element. You will need to add either a `class` or an `id` to it in order to access it, like so: `$(“.posts”)`. Now that you have access to the element that you made to put all the posts in, you can `append` them to that element. 

At this point, if everything works, you should be able to run your code and see it being added to your webpage without refreshing. Once you do refresh the page, everything will revert back to the original layout. When doing Javascript and JQuery, it’s only temporary, unless you’ve persisted the information to a database, and have code in place to render that information.

JQuery can be intimidating, especially when it’s completely new to you. But if you understand Rails, it’s really not that different. The only difference is how things are shown in the browser. With Rails, you redirect to a new page, and have all the information in the view file. With JQuery, you don’t redirect to a new page, but instead take the information and put it into the already existing HTML for that page. 
