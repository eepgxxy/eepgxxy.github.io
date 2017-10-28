---
layout: post
title:  "Changing 'this' When Invoking a Function"
date:   2017-07-20 23:00:00 +0800
categories: blog
id: 40
---

'*This*' is the key word in JavaScript to refer to the object that invokes a function. Normally a function is bound to an object from which it is being invoked. If the function is a method of an object, that object is responsible for invoking the function. Otherwise, the global object, normally the *window* object becomes the default object. Sometimes we need to change the object to another object for invoking the function. This is normally required when we want to apply the method of an object to another object.

There are three methods being built in JavaScript to finish the "changing invoking object" task. They are *call*, *apply* and *bind*. Let's look at them one by one.

* The *apply* method

apply() is the method of any functions. It takes two parmeters, the object to be used as the function context, and an array of values to be used as the invocation arguments.Talk is cheap. So let me show you by a few lines of codes how *apply* works.

{% highlight javascript %}
function add(){
    var result = 0;
    for(i = 0; i < arguments.length; i++) {
        result += arguments[i];
    }
    this.result = result;
}
var obj1 = {};
add.apply(obj1, [1, 2, 3, 4]);
console.log(obj1.result);
{% endhighlight %}

* The *call* method

The *call* method is very similar to the *apply* method, except that it takes a list of arguments directly instead of an array of arguments.

{% highlight javascript %}
function add(){
    var result = 0;
    for(i = 0; i < arguments.length; i++) {
        result += arguments[i];
    }
    this.result = result;
}
var obj2 = {};
add.call(obj2, 1, 2, 3, 4);
console.log(obj2.result);
{% endhighlight %}

* The *bind* method

The *bind* method is different from *call* and *apply* by returning a function binded to the invoking context as the first parameter of its arguments and passing parameters as its other arguments.

{% highlight javascript %}
function add(){
    var result = 0;
    for(i = 0; i < arguments.length; i++) {
        result += arguments[i];
    }
    this.result = result;
}
var obj3 = {};
var newFunc = add.bind(obj3, 1, 2, 3, 4);
newfunc();
console.log(obj3.result);
{% endhighlight %}

The *bind*, *call* and *apply* are all the methods that are built-in methods for all the functions. They also tell us that **functions** are first-class objects in JavaScript.

