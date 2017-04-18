---
layout: post
title:  "First Look at AngularJS"
date:   2017-04-16 23:00:00 +0800
categories: blog
id: 30
---
*AngularJS* is by far the most popular JavaScript framework. Comparied with JavaScript libraries such as jQuery, JavaScript frameworks provide more functionalities, mainly design patterns, to web developers. By using JavaScript frameworks, developers can work with web apps, mobile apps, desktop apps, even server side code in a more maintainable way, especially for *SPAs(Single Page Applications)*. 

*AngularJS* was developped in 2009 and strongly supported by Google. *Angular 2* was coming out in 2015 with almost completely new architectures and features. Starting from this post, I am writing a series of posts on *Angular 1* which is also often called *AngularJS* :link:[angularJS][angularJS].

*AngularJS* is based on the design pattern of *MVC* or *MVVM*. This concept was originally being used on the back-end by software developers. *MVC* is an abbreviation for *Model, View, Controller*. The basic idea is that *All the data should be going from Model through Controller to View and vice versa*. By following this pattern, the code is more readable and maintainable when web application is being large scaled.

The key features of *AngularJS* are:

* Two-way data binding:

Two-way data binding allows for automatic data update on both *Model* and *View* whenever there is a data change. In this way, traditional DOM manipulation of adding and removing is no longer necessary. All you need to do is updating the HTML template through *Controllers*.

{% highlight html %}
<!DOCTYPE html>
<html lang="en" ng-app="myApp">
<head>
  <meta charset="UTF-8">
  <title>angularjs</title>
</head>
<body ng-controller="myCtrl">
  <h1>This is angularjs two-way data binding</h1>
  <input type="text" ng-model="yourName">
  <p>
    Hello  {{yourName}}
  </p>
  <script src="lib/angular.min.js"></script>
  <script src="js/app.js"></script>
</body>
</html>>
{% endhighlight %}

{% highlight javascript %}
angular.module("myApp", [])
       .controller("myCtrl", ['$scope', function($scope) {
          $scope.name = "Xiaoming";
       }]);
{% endhighlight %}
* Dependency injection:

Dependency injection is a way of injecting(providing) the dependencies(needed modules, normally JS files or functions) to the *modules*, *controllers* or *services* whenever required. It is a concept that is better understood by showing real code like follows:

{% highlight javascript %}
angular.module('myApp', ['ngRoute', 'ngAnimate']);
{% endhighlight %}


* Extending HTML vocabulary

*AngularJS* lets you write your own HTML tags which are called *Directives* in angular's words. In this way, you can extend the HTML vocabulary by inventing new HTML syntax thus build the *View* the way your want and reuse it whereever needed in your project.

You first need to define your own HTML tags in *Controller* like follows:

{% highlight javascript %}
app.directive('myTag', function(){
    return {
      restrict: 'E',
      template: '<div>This is my tag</div>'
    };
});
{% endhighlight %}

Then you can use your own HTML tags in *Views* like follows:

{% highlight html %}
<my-tag></my-tag>
{% endhighlight %}

The above three features are the main pros for *AnguarJS*. It is really worth trying if you haven't used it before.

[angularJS]:https://angularjs.org/