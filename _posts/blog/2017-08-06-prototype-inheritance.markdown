---
layout: post
title:  "Inheritance Based on Prototype"
date:   2017-08-06 23:00:00 +0800
categories: blog
id: 44
---

Prototype is the unique feature of JavaScript used for inheritance. JavaScript is an object based programming languange. However, there is no definition of *class* as those traditional class based programming languages such as C++ and Java. In order to minic the features of class, JavaScript uses *prototype*.

Prototype is the feature of a function when the function is being used as a *constructor* function. When a function is invoked as a constructor function, the *this* is bound to the newly created object instance for instantiation. And the newly created object gets inheritance not only from the parent constructor function but also from the prototype property of the parent constructor function. This is called prototype inheritance.

{% highlight javascript %}
function Person(){}
Person.prototype.walk = function(){return true;};
var person1 = new Person();
person1.walk(); // true
{% endhighlight %}

* Properties in constructors take precedence over those of prototypes

When the name of a property or method is identical to that of property or method on the prototype. The properties of constructor function always overide those of its prototypes.

{% highlight javascript %}
function Person(){this.walk = function(){return false;}}
Person.prototype.walk = function(){return true;};
var person1 = new Person();
person1.walk(); // false
{% endhighlight %}

* Prototype values are referenced instead of copied to the newly created instance

Even if the object is created before the prototype properties are added. The object can always get access to the prototype properties.

{% highlight javascript %}
function Person(){}
Person.prototype.walk = function(){return true;};
var person1 = new Person();
person1.walk(); // true
Person.prototype.walk = function(){return false;};
person1.walk(); // false
{% endhighlight %}

* Prototype chain

So how the object find which property value it should use when it need to access a property name. Here comes the prototype chain.

When a property value is needed, the object first looks at its own properties list, if it finds the properity name, the value is used. Otherwise, its constructor's prototype is searched, if it finds the properity name, the value on the constructor's prototype is used. Otherwise, its constructor's constructor's prototype is searched and so on until the prototype of the *Object* is searched. If nothing is found along the prototype chain, then *undefined* is returned.

{% highlight javascript %}
function Person(){}
function Human(){}
Human.prototype.breathe = function(){console.log("breathing");};
Person.prototype = new Human();
var person1 = new Person();
person1.breathe(); // breathing
{% endhighlight %}

