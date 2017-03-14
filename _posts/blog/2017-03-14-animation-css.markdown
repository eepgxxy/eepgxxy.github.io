---
layout: post
title:  "Web Animation using CSS"
date:   2017-03-14 20:30:00 +0800
categories: blog
id: 20
---
*Animation on the web* is a big topic for web design and development. Starting from this post, I will start a series of writings devoted to the animation on the web. Animation can make the web page dynamic, attracting, beautiful and holding more customers. Animation is also a key factor for web based game design and development. Different techniques can be used to make animations. In this post, I explain how to make animations using CSS.

We all know the `:hover` pseudo-class produce a state-change effect for HTML element. However, It is not actually animations. There is no duration between the state-change. *CSS transition* is the CSS property to add the duration needed for animation. Besides, *CSS3* also provides `transform`, `keyframes` and `animation` properties.

* :bell:CSS transition:

There are four CSS transition properties available, `transition-property`, `transition-duration`, `transition-timing-function` and `transition-delay`. They can also be abbreviated to a single `transition` property. More transition-timing-function `cubic-bezier` values can be found in :link:[cubicbezier][cubicbezierref].

{% highlight css %}
div {
    width: 400px;
    height: 400px;
    background-color: #f00;
    /*
    transition-property: background-color;
    transition-duration: 2s;
    transition-timing-function: ease-in-out;
    transition-delay: 1s;
    */
    transition: all 2s ease-in-out 1s;
}
div:hover {
    width: 200px;
    height: 200px;
    background-color: #00f;
}
{% endhighlight %}

* :bell:CSS transform:

CSS transform is a css property to change the state of the HTML element. There are four different values for this property: `translate(x, y)`, `rotate(xdeg)`, `skew(xdeg)`, `scale(x, y)`.

{% highlight css %}
div {
    transition: all 2s cubic-bezier(.3, .4, .5, .6), 1s;
}
div:hover {
    transform-origin: bottom left;
    transform: rotate(45deg) skew(10deg, 20deg) translate(100px, 100px) scale(.5, .5);
}
{% endhighlight %}

* :bell:CSS keyframes:

Any animation is just a series of keyframes. CSS3 provides the `@keyframes` rule to define different intermediate stages of animation keyframes.

{% highlight css %}
@keyframe mykeyframe {
    0% {
        top: 0; left: 0;
    } 
    50% {
        top: 100px; left: 200px;
    }
    100% {
        top: 200px; left: 500px;
    }
}
div {
    animation: mykeyframe cubic-bezier(.8, .5, .3, .7) 5s infinite alternate;
}
{% endhighlight %}

* :bell:CSS media queries:

Media queries are originaly designed for responsive web design and are still using for this purpose. By thinking the way how media qurie works, animations can be designed when the web page's size is being constantly adjusted, though it is not strictly an animation by definition.

{% highlight css %}
@media screen and (min-width: 500px) {
    div {
        background-color: #f00;
    }
}
@media screen and (min-width: 600px) {
    div {
        background-color: #00f;
    }
}
@media screen and (min-width: 700px) {
    div {
        background-color: #0f0;
    }
}
{% endhighlight %}

These are just basic ways to make animations using CSS.:tada:

[[cubicbezierref]]: http://cubic-bezier.com
