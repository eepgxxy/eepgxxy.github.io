---
layout: post
title:  "Data Types in JavaScript"
date:   2017-08-05 23:00:00 +0800
categories: blog
id: 43
---

There are five primitive data types and one reference data types in JavaScript. This is the foundation for JavaScript. The primitive data types are *Number*, *String*, *Boolean*, *Null* and *Undefined*. The reference data type is *Object*. However, there are also six data types in the *Object* category and they are actually diferrent reference data types. They are *Object*, *Function*, *Array*, *Error*, *Date* and *RegExp*

* Number

All numbers including both integer numbers and floating point numbers are of type *Number*.

{% highlight javascript %}
typeof 1 //"number"
{% endhighlight %}

* String

String is the character set that is enclosed by single quotes or double quotes.

{% highlight javascript %}
typeof "hello" //"string"
{% endhighlight %}

* Boolean

The boolean data type has only two values, *true* and *false*. However, other values in JavaScript can also be interpreted as either *true* or *false* in developement.

{% highlight javascript %}
typeof true //"boolean"
{% endhighlight %}

* Null

There is only one value for the *Null* data type, *null* which stands for an empty object.

{% highlight javascript %}
null === null //true
{% endhighlight %}

* Undefined

When a variable is defined but not initialized, its value is *undefined*.

{% highlight javascript %}
typeof undefined //"undefined"
{% endhighlight %}

From the above codes we can see that the primitive types can be determined by the operator `typeof` except the *null* which can be determined by getting the returned value of comparing it to *null* using `===`.

To determine the types of a reference data type is not as easy as the primitive types. If you use `typeof`, you will simply get `object` except the *Function* data type for which you get `function`. So what should we do to tell their data types? The answer is using `instanceof` operator.

{% highlight javascript %}
var a = new Object(),
    b = new Function(),
    c = new Array(),
    d = new Date(),
    e = new Error(),
    f = new RegExp();

a instance of Object //true
b instance of Function //true
c instance of Array //true
d instance of Date //true
e instance of Error //true
f instance of RegExp //true
{% endhighlight %}

You may wonder if there is a universal way to test the data type of a variable. The answer is *no* at the moment. However, you can rely on the following code to test a data type most of the time.

{% highlight javascript %}
function test(value) {
    var result = Object.prototype.toString.call(value);
    return result.substring(8, result.length - 1);
}
var a = new Object(),
    b = new Function(),
    c = new Array(),
    d = new Date(),
    e = new Error(),
    f = new RegExp(),
    g = 1,
    h = "string",
    i = true,
    j = null,
    k = undefined;

test(a) //"Object"
test(b) //"Function"
test(c) //"Array"
test(d) //"Date"
test(e) //"Error"
test(f) //"RegExp"
test(g) //"Number"
test(h) //"String"
test(i) //"Boolean"
test(j) //"Null"
test(k) //"Undefined"
{% endhighlight %}

