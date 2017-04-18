---
layout: post
title:  "Ajax in AngularJS"
date:   2017-04-18 23:00:00 +0800
categories: blog
id: 31
---
*AngularJS* is terrific for client-side web programming, especially for *SPA*. However, it is no use without the data from the server-side. Ajax is a great tool for retrieving and sending data between the client-side and the server-side. Using **ajax** in **angularJS** is easy. 

**$http** is the method or a built-in service in *angularJS* for making ajax calls. The example codes are as follows:

{% highlight javascript %}
$http({method: "GET", url: "data.json"})
.then(function(response){
    console.log(response);
}, 
function(error){
    console.log(error);
});
{% endhighlight %}

Or you can also write ajax in another way:

{% highlight javascript %}
$http.get("data.json")
.then(function(response){
    console.log(response);
}).catch(function(error){
    console.log(error);
});
{% endhighlight %}

This works if you put `$http` service in your *Controller* file. However, if you make the ajax call in your custom defined *Services*, then things will be different because of the asynchronous nature of ajax. 

Returning data from service to controller in *angularJS* can be hard at first sight, because the returned data is no longer being visible (being **undefined**) when the controller begins use it. There are three solutions to the above mentioned problem:

* Utilizing the $q service

{% highlight javascript %}
myApp.factory('myService', function($http, $q){
    var deferred = $q.defer();
    var promise = deferred.promise;

    $http.get('/a').then(function(response) {
      deferred.resolve({
        mydata: response.data,
      });
    }).catch(function(error) {
      deferred.reject();
    });
    return promise;  
});
{% endhighlight %}

Then in the controller file, the returned *promise* can be used by *then()* method:

{% highlight javascript %}
myApp.controller('myController', ['$scope', 'myService', function($scope, myService){
  myService.then(function(result) {
    $scope.data = result.mydata;
  });
}]);
{% endhighlight %}

* Utilizing a callback function

{% highlight javascript %}
myApp.factory('myService', function($http){
    return {
      getInfo: function(successcb) {
        $http.get('/a').then(function(response) {
          return successcb({mydata: response.data});
        }).catch(function(error) {
          console.log(error);
        });
    }
  };
});
{% endhighlight %}

The controller code for this second solution is shown below:

{% highlight javascript %}
myApp.controller('myController', ['$scope', 'myService', function($scope, myService){
  myService.getInfo(function(result) {
    $scope.data = result.mydata;
    $scope.status = result.mystatus;
  });
}]);
{% endhighlight %}

* Utilizing the $resource service

For this solution, what you need to do is two steps:

1. Include the 'angular-resource.min.js' in the *html* file
2. Inject the module dependency to the module creation js file like follows:

{% highlight javascript %}
var eventsApp = angular.module('eventsApp', ['ngResource']);
{% endhighlight %}

3.Create the *$resource* service in the service js file:

{% highlight javascript %}
eventsApp.factory('eventData', function($resource){
  return {
    getEvent: function() {
      return $resource('js/data/event/a.json');
    };
  });
{% endhighlight %}

4.Inject the *$resource* service into the controller js file:

{% highlight javascript %}
  $scope.event = eventData.getEvent().get(function(response) {
    console.log(response);
  }, function(error) {
    console.log(error);
  });
{% endhighlight %}

