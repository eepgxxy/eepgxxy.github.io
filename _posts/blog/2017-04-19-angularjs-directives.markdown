---
layout: post
title:  "Directives in AngularJS"
date:   2017-04-19 23:00:00 +0800
categories: blog
id: 32
---
*Directives* is the AngularJS preferred method for building reusable components. This is one of the key features of AngularJS for extending HTML vocabulary. *Directives* combine the HTML template and the definitions in Controller together. AngularJS has also a lot of built-in directives. The *ng-repeat*, being used in the last post, is one of them. In fact, *Ng* prefixed items in templates are all directives. We can also define custom directives in the Controller.

Custom defined directives usually take different forms: as element, as attribute, as class, as comment or as any combination of them. The following code defines directive as element.

{% highlight javascript %}
app.directive('myTag', function(){
  // Runs during compile
  return {
    restrict: 'E', // E = Element, A = Attribute, C = Class, M = Comment
    template: '<div>This is my tag</div>'

  };
});
{% endhighlight %}

After definition, we can use the directive in the `html` template:

{% highlight html %}
<my-tag></my-tag>
{% endhighlight %}

Similarly, you can define custom directive as attribute:

{% highlight javascript %}
app.directive('myTag', function(){
  // Runs during compile
  return {
    restrict: 'A', // E = Element, A = Attribute, C = Class, M = Comment
    template: '<div>This is my tag</div>'

  };
});
{% endhighlight %}

Then you can use it in html file as follows:

{% highlight html %}
<div my-tag></div>
{% endhighlight %}

Interestingly, AngularJS can also manipulate DOM in directive definitions. The way is to use the `link` option.

{% highlight javascript %}
app.directive('newOne', function(){
  // Runs during compile
  return {
    restrict: 'C', // E = Element, A = Attribute, C = Class, M = Comment
    template: 'hello world',
    // compile: function(tElement, tAttrs, function transclude(function(scope, cloneLinkingFn){ return function linking(scope, elm, attrs){}})),
    link: function($scope, iElm, iAttrs, controller) {
      iElm.text("Good bye");
    }
  };
});
{% endhighlight %}

The `html` template is:

{% highlight html %}
<div class="new-one"></div>
{% endhighlight %}
