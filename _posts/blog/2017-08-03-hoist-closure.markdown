---
layout: post
title:  "Hoisting and Closures in JavaScript"
date:   2017-08-03 23:00:00 +0800
categories: blog
id: 42
---

Hoisting and closures are the two features that JavaScript have and confuse the beginners. They are the features a professional JavaScript programmer must know.

Hoisting and closures are both related to functions, and especially refer to scopes in functions.

Scopes in JavaScript are defined by functions, not by braces as in C language.

* Hoisting

Hoisting refers to the case that named functions are in scope within the entire function within which they are declared.

{% highlight javascript %}
function outer() {
    var a = 1;
    function inner() {
        console.log(a, b, c);
    }
    inner();//1,undefined,undefined
    var b = 2;
    if(a == 1) {
        var c = 3;
    }
    inner();//1, 2, 3
}
outer();
{% endhighlight %}

* Closure
Closure refers to the case that variables being defined within its functional scope can only be accessed from its scope but not outside of its scope.

Closures can be best used for protecting some variables by making them being private.

{% highlight javascript %}
var person = (function(){
    var age = 20;
    var getAge = function(){
        return age;
    };
    var setAge = function(value){
        age = value;
        return age;
    };
    return {
        getAge: getAge,
        setAge: setAge
    };
}());
person.getAge();//20
person.setAge(21);//age becomes 21
{% endhighlight %}

From the above example we can see that closure is closely related to IIF(Immediatelly Invoked Function).When IIF is used, a closure is being created automatically. Actually that's the main application scenario for IIFs.
