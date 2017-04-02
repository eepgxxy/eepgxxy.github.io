---
layout: post
title:  "Web Animation Using GSAP"
date:   2017-03-19 22:30:00 +0800
categories: blog
id: 23
---
*GSAP* stands for *GreenSock Animation Platform*. It is a very efficient and high performance HTML5 animation library, lightweight and fast. It is the best JavaScript animation library that I have used. :link:[GSAP][GSAP].

*GSAP* is also very easy to use. All you need to do is incorporating the library to your HTML file and starting using the APIs. Don't worry if you see a lot of JavaScript files from the downloaded zip file from the *GSAP* website. Just use *TweenMax.min.js* will be a safe to go. The following code shows a red ball circulating around the center of the box. It can be regarded as a simple replica of the one I did for the canvas game in the post of March 15th 2017. For brevity, the HTML and CSS codes are ommited and *jQuery* is being used by default.

{% highlight javascript %}
var ball = $("#ball");
var tl = new TimelineMax(); //Create a TimelineMax object
tl.to(ball, 4, {       
    bezier: { //define the curve for the ball to follow
        type: "thru",
        curviness: 2,
        autoRotate: 45,
        values: [
            {left: 450, top: 300},
            {left: 300, top: 450},
            {left: 150, top: 300},
            {left: 300, top: 150},
            {left: 450, top: 300}
        ]
    },
    repeat: -1, //repeate infinitely
    ease: Linear.easeNone
    });
$(".btn-pause").click(function() { //click to pause the animation
    tl.pause();
});
$(".btn-resume").click(function() { //click to resume the animation
    tl.play();
});
$(".btn-reverse").click(function() { //click to reverse the animation
    tl.reverse();
});
{% endhighlight %}

There are indeed not much to say about the code above. Because it explains all by itself. You can do so much animation by using the free version of the *GSAP*. If you want to do more and for your business use, you can pay to get the paid bonus to get more features for animation. However, I do think it is worth the price.

To recap:

* :bell:*GSAP* libraries contains: `TimelineLite`, `TimelineMax`, `TweenLite` and `TweenMax`. `Lite` is just a lightweight version compared with `Max`
* :bell:*GSAP* also has plugins for extended features such as animating CSS rules
* :bell:*GSAP* has more features such as *physics* in paid bonus versions

[GSAP]: https://greensock.com/
