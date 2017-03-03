---
layout: post
title:  "Digging into the Programming Paradigm for Javascript"
date:   2017-03-03 20:06:00 +0800
categories: blog
---
Programming paradigm is a huge topic that can not be easily covered in this single post. I am here just introduce the basic ideas of it for Javascript programming, mainly *Object Oriented Programming* and *Functional Programming*.

* Object Oriented Programming in Javascript:

Javascript is not an *Object Oriented Language*. However, everything in Javascript can also be regarded as an Object. *Object Oriented Programming* is best used for modelling different objects. The following codes show how to do Javascript programming using the *Object Oriented Programming Paradigm*.

>function Person(name, age) {
>    this.name = name;
>    this.age = age;
>    this.introduce = function() {
>        console.log("My name is " + this.name + " and I am  " + age + " years old.");
>    }
>} 
>    var xiaoming = new Person("xiaoming", 21);
>    xiaoming.introduce();

* Functional Programming in Javascript:

*Functional Programming* is another paradigm that can be used in Javascript. And most people are doing this even without realizing that they are actually using the paradigm. *Functional Programming* is best used for modelling different tasks. The following codes show how to loop through a group of HTML elements using *Functional Programming* instead of normal *for loops*.

> var elements = document.querySelectorAll("li");
>   Array.prototype.map.call(elements, function(elem, index) {
>      elem.innerText = "This is element " + index;
>  });

Neither *Object Oriented Programming* nor *Functional Programming* is absolutely right in every situation. The only right way is to use the right paradigm in the right situation.:older_man:
