---
layout: post
title:  "Web Animation Using JavaScript"
date:   2017-03-15 21:30:00 +0800
categories: blog
id: 21
---
*JavaScript* is powerful enough to do any animations on the web. However, using plain vanilla JavaScript to do the job may let us feel frustrating. Because there are just so much to do to make a big fantastic animation. This post just digs into the shallow but essential part of the deep water of JavaScript animation. 

*Animation* is just a series of movements or state changes following the timeline. In JavaScript, `setTimeout` and `setInterval` are two functions to deal with time and they are essential to making animations. With the power of these two functions, you can make any animation by changing the position, color, behavior and any other properties of the HTML element.

The following example shows a basic animation by using `setInterval` and *canvas* API.

* :bell:Animation showing red ball constantly rotating around the center of the canvas:

{% highlight javascript %}
var canvas = document.querySelector("#myCanvas");
    var ctx = canvas.getContext("2d");
    var deg = 0;

    ctx.save();
    ctx.beginPath();
    ctx.translate(300, 300);
    ctx.arc(150, 150, 50, 0, 2*Math.PI, true);
    ctx.fillStyle = "#f00";
    ctx.fill();

    var m = setInterval(draw, 50);
    function draw() {
        ctx.restore();
        ctx.clearRect(0, 0, 600, 600);
        ctx.save();
        ctx.translate(300, 300);
        ctx.rotate(deg += Math.PI/10);
        ctx.beginPath();
        ctx.arc(150, 150, 50, 0, 2*Math.PI, true);
        ctx.fillStyle = "#f00";
        ctx.fill();
    }
{% endhighlight %}

As `setInterval` is not an optimized way to make animations, we can utilize the `requestAnimationFrame` method to make our simulation run smoother. The changed code is:

{% highlight javascript %}
var m = setInterval(function() {
    window.requestAnimationFrame(draw);
}, 50);
{% endhighlight %}

We can even use the `requestAnimationFrame` method solely without the `setInterval` if all we want is a smooth optimized animation with 60 frames per second. In this case, the changed code  will be:

{% highlight javascript %}
window.requestAnimationFrame(draw);
function draw() {
    ctx.restore();
    ctx.clearRect(0, 0, 600, 600);
    ctx.save();
    ctx.translate(300, 300);
    ctx.rotate(deg += Math.PI/10);
    ctx.beginPath();
    ctx.arc(150, 150, 50, 0, 2*Math.PI, true);
    ctx.fillStyle = "#f00";
    ctx.fill();
    window.requestAnimationFrame(draw);
}
{% endhighlight %}

To make more complex animations easier, people developed different Javascript libraries. Some are general, like :link:[jQuery][jQuery] and others are dedicated, like :link:[GSAP][GreenSock]. We will explore more of those later.

[jQuery]: http://www.jquery.com
[GreenSock]: https://greensock.com/
