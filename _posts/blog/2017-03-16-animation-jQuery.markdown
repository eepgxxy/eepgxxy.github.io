---
layout: post
title:  "Web Animation Using jQuery"
date:   2017-03-16 21:30:00 +0800
categories: blog
id: 22
---
*jQuery* is the most popular JavaScript library used in the web. As newer front-end frameworks arrives and becomes popular, some think *jQuery* is old style and does not meet the current web's requirements. However, in my opinion, *jQuery* is still valuable and should be used in some situations. Animations may be one of those.

*jQuery* has the built-in `animation()` function to animate different properties of HTML elements on the web as shown in the following code. One thing to be noted is that the non-numeric property values can not be animated, such as `backgroundColor`.

{% highlight css %}
$('#element').animate({
    width: "400px",
    height: "300px",
    left: "400px"
}, 2000, "swing")
{% endhighlight %}

*jQuery* has also other functions with similar animation effects, such as `fadeIn()`, `fadeOut()`, `slideDown()`, `slideUp()`, etc..

Besides, there a lot of *jQuery* plugins with animation effects. To name few:

* :bell:jQueryUI for making tabs, accordions and other UI elements:link:[website][jQueryUI]
* :bell:jQuery-cycle2 for carousels and slide shows:link:[website][cycle2]
* :bell:fresco for making beautiful lightboxes:link:[website][fresco]
* :bell:waypoints for triggering elements when scrolling the scroll bar:link:[website][waypoints]
* :bell:Stellar for creating parallax effect:link:[website][stellar]

A fairely complete but not exhausted list of animation related jQuery plugins is on this website:link:[animation taged jQuery plugins][animationjQueryPlugins] 

[jQueryUI]: https://jqueryui.com/
[cycle2]: http://jquery.malsup.com/cycle2/
[fresco]: http://www.frescojs.com/
[waypoints]: http://imakewebthings.com/waypoints/
[stellar]: http://markdalgleish.com/projects/stellar.js/
[animationjQueryPlugins]: https://plugins.jquery.com/tag/animation/
