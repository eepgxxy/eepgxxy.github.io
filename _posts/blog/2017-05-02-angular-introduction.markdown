---
layout: post
title:  "Introduction to Angular - Version 2 and Beyond"
date:   2017-05-02 23:00:00 +0800
categories: blog
id: 36
---

*Angular* is the word for referring to the Angular version 2 and beyond, while *angularJS* is speciffically referring to the angular version 1. *Angular* is different from *angularJS* both from inside and from outside. It can even be regarded as a totally different framework compared to *angularJS*;

The key difference is that *angularJS* is tightly coupled with the *DOM* while *angular* is not. This strict coupling restricts *AngularJS* to the browser side application development. *Angular*'s goal is to break that tie and make itself to be available in other platforms such as mobile terminals and server side.

There are eight main parts for the *angular* architecture:

* Module
* Component
* Template
* Metadata
* Data Binding
* Service
* Directive
* Dependency Injection

![Arch of Angular](/images/archOfAngular2.jpg)

You cannot say that you know *angular* except that you know the following key concepts which are being used in *angular*:

* TypeScript

This is the main scripting language being used in angular.

* Component

This brings power to angular and make it being cross-platform.

* Angular-CLI

This is the command-line tool that help you in your end-to-end workflow.

Now you have a basic idea of what *angular* is. It is time to start your own first *angular* application using the following steps:

{% highlight bash %}
npm install -g angular-cli
ng new project_name
ng serve --open
{% endhighlight %}

Now that you should already have your first *Angular* application running in the browser. However, what does the *Angular* framework offer to you in summary?

* Dynamic HTML
* Powerfull templates
* Fast rendering
* HTTP services
* Component encapsulation
* Form & input handling
* Event handling
* Routing
* Lastest JavaScript standards such as ES6 and TypeScript
* Much much more...

