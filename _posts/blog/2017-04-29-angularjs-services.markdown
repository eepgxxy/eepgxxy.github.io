---
layout: post
title:  "Services in AngularJS"
date:   2017-04-29 23:00:00 +0800
categories: blog
id: 33
---
*Service* in AngularJS is the functional block for providing data to components(controllers, services, filters or directives) across your app. You can write your own services. You can also use the built-in services in AngularJS, like $http. To use a service, you need to add it as a dependency for your component.

The steps for creating and using a service are as follows:

* Creating a service

{% highlight javascript %}
app.service('myService', function(){
  // Runs during compile
  return {
    name: xiaoming
  };
});
{% endhighlight %}

* Using a service

{% highlight javascript %}
app.controller('myCtrl', ['$scope', 'myService', function($scope, myservice) {
  $scope.name = myService.name;
}]);
{% endhighlight %}

You can also use the method `factory` to register a service as follows:

{% highlight javascript %}
app.factory('myService', function(){
  // Runs during compile
  return {
    name: xiaoming
  };
});
{% endhighlight %}

As I said, you can also use many of the AngularJS built-in services. The ones you may use frequently are `$http`, `$q`, `$animate`, `$log`, $timeout`, `$window` and `$rootScope`, etc..
