---
layout: post
title:  "Routers in AngularJS"
date:   2017-04-30 23:00:00 +0800
categories: blog
id: 34
---
*Routers* are designed to make your web apps *SPA* so that you view your page based on different routes instead of different pages. However, the *Routers* in AngularJS have been changed to be compatible with the routers in Angular.

In AngularJS, the router is not inside the angularJS core library. So, in order to use routers, you need to add `angular-route.js` in your HTML file as folows.

{% highlight html %}
<script src="path/to/angular.js"></script>
<script src="path/to/angular-route.js"></script>
{% endhighlight %}

To configure the routes you need to set the directive `$routeProvider` as a dependency. The example code is as follows:

{% highlight javascript %}
app.config(function($routeProvider){
  $routeProvider
    .when('/test/:stuId', {
      templateUrl: 'test.html',
      controller: 'StuCtrl'
    })
    .when('/test/:infoId', {
      templateUrl: 'info.html',
      controller: 'InfoCtrl'
    });
});
{% endhighlight %}

