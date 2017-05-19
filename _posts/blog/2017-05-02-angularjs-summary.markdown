---
layout: post
title:  "Summary to AngularJS"
date:   2017-05-02 23:00:00 +0800
categories: blog
id: 36
---
*AngularJS* is a fairly complex front-end framework. There are a lot of things you need to pay attention to.Therefore it is necessary to give a summary to this framework and this post is devoted to this. One post is actually too short for the summary to this huge framework. Here we only summarize some of the pitfalls of this framework so that you can avoid these and explore more of it yourself later.

* Different versions are really different:

The newest version of *AngularJS* up to the writing of this post is version 1.6.4. Different versions are different even though they belong to the same version 1.x category. This means that the code that works for version 1.4 may not work for 1.6.  For example, you need to use `$locationProvider.hashPrefix("")` in order for routing to work in version 1.6 but you can ommit it in version 1.4 and 1.5. There are also other tricky things you need to care about. 

For more information, please consult the *angularJS* website [angularjs][angularjs].

* Abstract the common things:

You may have a lot of common things among different pages in your project, for example the part of header and footer. One good way to make your project more concise and more maitainable is to make the common things become seperate templates and then include those templates in your pages. The following code shows this:

{% highlight javascript %}
<div ng-include="'tpl/header.html'"></div>
<div ng-include="'tpl/footer.html'"></div>
{% endhighlight %}

* Making fully use of ngAnimate:

*ngAnimate* can be fully used to make your web pages more user-friendly. There two ways to utilize the *ngAnimate* module. One is the *CSS way* and the other is the *JavaScript way*. The example code of the *CSS way* is as follows:

{% highlight css %}
.index-page {
  position: absolute;
  width: 100%;
}
.index-page.ng-enter,
.index-page.ng-leave {
  transition: all .5s linear;
}
.index-page.ng-enter {
  left: 100%;
  opacity: 0;
}
.index-page.ng-enter-active {
  left: 0;
  opacity: 1;
}
.index-page.ng-leave {
  left: 0;
  opacity: 1;
}
.index-page.ng-leave-active {
  left: -100%;
  opacity: 0;
}
{% endhighlight %}

* Always seperate *Controllers*, *Services* and *Directives*:

It is a good practice to seperate controllers, Services and Directives, etc. and put them into different JavaScript files. An example of `index.html` file is as follows:

{% highlight html %}
<script src="js/app.js"></script>
<script src="js/directive.js"></script>
<script src="js/service.js"></script>
<script src="js/controller.js"></script>
{% endhighlight %}

[angularjs]: https://angularjs.org/