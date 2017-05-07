---
layout: post
title:  "Filters in AngularJS"
date:   2017-05-01 23:00:00 +0800
categories: blog
id: 35
---
*Filter* is also a component in the AngularJS framework. It is used for post-processing the expressions or values. Similar as services, you can define your own filters and you can also use the built-in filters.

* Defining a filter

{% highlight javascript %}
app.filter('uppercase', function(){
  return function(input) {
    input = input || '';
    var out = '';
    out = input.toUpperCase();
    return out;
  };
});
{% endhighlight %}

* Using a filter in the controller
{% highlight javascript %}
app.controller('MainCtrl', ['$scope', 'uppercase', function($scope, uppercase) {
  $scope.greeting = 'hello';
  $scope.uppcaseGreeting = uppercase($scope.greeting);
}]);
{% endhighlight %}

* Using a filter in the view

{% highlight html %}
<div ng-controller="MainCtrl">
  <input ng-model="greeting" type="text">
  <p>{{greeting | uppercase}}</p>
</div>
{% endhighlight %}
