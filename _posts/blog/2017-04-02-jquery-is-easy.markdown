---
layout: post
title:  "Learning jQuery is Easy"
date:   2017-04-02 16:00:00 +0800
categories: blog
id: 27
---
*jQuery* is probably by far the most popular javascript library for web developers. And it is also very easy to use. The slogan of *jQUERY* is *"write less, do more"*. With just a few lines of *jQuery* codes, you can do a lot of things that will normally take you more lines of codes and more time to finish. So there is really no reason that we should not use *jQuery*. However, people find that *jquery* does have drawbacks recently and begin using other frameworks. I will come to the other frameworks in my later posts. In this post, I am only focusing on the good parts of *jQuery*:link:[jQuery][jQuery].

* :bell: Install and use jQuery

Using automation tools such as *bower* and *npm* is one way to use *jQuery*(the way I prefer).You can also download the jQuery .js file directly from the jQuery website and then include it in the HTML file and start using it as follows: 

{% highlight html %}
<html>
<head>
<script src="jquery.js"></script>
</head>
<body>
<script>
$(function() {
  // Tasks to be done when DOM is ready
}());
</script>
</body>
</html>
{% endhighlight %}

The basic syntax for jQuery is:

{% highlight javascript %}
$(selector).action();
{% endhighlight %}

* :bell: Selecting DOM elements

In fact, the most useful thing of *jQuery* is to select DOM element using CSS selector syntax. For example:

{% highlight javascript %}
$("p").fadeOut() 
// This will fade out all p tag HTML elements 
$(".example").fadeOut() 
// This will fade out all the HTML elements with class "example" 
$("#example").fadeOut()
// This will fade out the HTML element which has an ID "example"
{% endhighlight %}

* :bell: jQuery DOM manipulations

Manipulating DOM elements is what *jQuery* is professional about. Moving, adding, removing and updating DOM become easy with *jQuery* functions. The most common jQuery DOM manipulation functions are `append()`,`after()`, `before()`, `attr()`, `css()`, `html()`, `val()`, `parent()`,`remove()`,`children()`, etc..

* :bell: Ajax operations

*jQuery* is skilled at Ajax operations. Everything needed for Ajax operations can be done by using just a single line of chained functions:

{% highlight javascript %}
$.ajax({
  url: '/path/to/file',
  type: 'default GET (Other values: POST)',
  dataType: 'default: Intelligent Guess (Other values: xml, json, script, or html)',
  data: {param1: 'value1'},
})
.done(function() {
  console.log("success");
})
.fail(function() {
  console.log("error");
})
.always(function() {
  console.log("complete");
});
{% endhighlight %}

* :bell: Cross browser support:

After using *jQuery*, cross browser and browser compatability issues are no long developers' headache. Forget about *Polyfills* and *Shims*. *jQuery* will handle all those things for you.

* :bell: jQuery plugins:

*jQuery* is already very powerful. *jQuery* plugins make it more powerful. You can even write your own *jQuery* plugins. You may have already felt the power of *jQuery* plugins from my previous posts about animations.

As one of the *cons*, people feel that *jQuery* is a little bit of heavy for light projects. And manipuating DOM a lot will be computing intensive for web pages. As an alternative, *Zepto* is more lightweight but less Internet Explorer friendly (Zepto doesn't support old Internet Explorer versions (<10)). Therefore, it is claimed to be a minimalist JavaScript library for modern browsers with a largely jQuery-compatible API:link:[Zepto][Zepto]. The other JavaScript frameworks provide either the similar functions as *jQuery*, such as *Angular*:link:[Angular][Angular], or alternative solution, such as *React*:link:[React][React].

As any other JavaScript libraries or frameworks, you can only get professional at it by using it. Old saying tells the truth again here: *Practice makes perfect*.:wink:

[jQuery]: http://jquery.com/
[Zepto]: http://zeptojs.com/
[Angular]: https://angular.io/
[React]: https://facebook.github.io/react/
