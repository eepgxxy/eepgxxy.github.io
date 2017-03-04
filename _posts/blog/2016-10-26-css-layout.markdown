---
layout: post
title:  "CSS Layout is Easier Than What You Think"
date:   2016-10-26 23:06:00 +0800
categories: blog
id: 13
---
CSS beginners are always frustrated with layout techniques when designing a web page. CSS layout is, in fact, much easier than what you think.

There are basically three different ways to do web page layout in CSS:

* :bell: Using "float"
* :bell: Using "position"
* :bell: Using "flex"

Up to now, I believe that "float" is still the most popular way to do css layout, though the promising "flex" is gradually catching up.

Let me explain briefly one by one.

To use "float", what you need is just giving every division that you want to position css rules "width: xxx" and float: left". That's pretty much what you need. Sometimes "clearfix" is needed to solve the problem of floated elements' parent container being collapsed.

"Position" is rarely being used to layout the whole web page. However, it is used sometimes for some particular elements, for example, when a fixed navbar is needed.

"Flex" is the promising and the suggested way to do the layout though browser support is not as good as the other two methods. It is easy to use and it solves the "clearfix" issue by itself automatically.

So my suggestions for css layout are as follows: 

* :ok_hand: Always use "float" when browser compatibility is the priority.
* :ok_hand: Try to use "flex" when backward compatibility is not your concern.
* :ok_hand: Only use "position" when necessary.

The last but not the least is "practice makes perfect" :secret:




