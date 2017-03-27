---
layout: post
title:  "The Principles of Responsive Web Design"
date:   2017-03-27 22:30:00 +0800
categories: blog
id: 25
---
Responsive Web Design or RWD in short is already a *by default* principle in web design and development. The phrase was coined not long ago in 2010. And it is said that it was first appeared in an article by *Ethan Marcotte* on *A List Apart*:link:[AListApart][AListApart]. 

RWD is refering to the design that a single web page can be shown optimized on different terminals, no matter it is desktop screen or mobile screens. Why do we need RWD? Because there are tons of different devices and sizes of screens and the number of those is still increasing. We need a way to adapt the single web page to the needs instead of creating an unlimited number of different versions of the same web page. So comes the RWD. 

The first-of-all principle for RWD is *relative sizing*. So you should always use relative sizing units like *em*, *rem* and *%* instead of absolute sizing units like *px*. The other main and basic principles of RWD can be based on these three different strategies: flexible grids, flexible images and media queries.

* :bell:The flexible grids:

The flexible grids means that the whole web page layout is devided into different number of grids. In this way, designing web layout becomes solving the issue of how to devide the whole page into different number of grids. 12 is the most commonly used number of grids. The *960 Grid Stystem* might be one of the first grids system:link:[960grids][960grids]. Recently *Bootstrap* is a more popular solution which including the 12 grids system, though you can customize the number of grids in the framework:link:[bootstrap][bootstrap]. 

* :bell:The flexible images:

The images on the web is not responsive by default. Responsive images are achieved by using CSS and the `<picture>` element. The following codes show an image with responsive sizing:

<% highlight css %>
img {
    max-width: 100%;
    height: auto;
}
{% endhighlight %}

'<picture>' element is a relatively new element and still not widely used.

<% highlight html %>
<picture>
    <source srcset="logos/logo_retina.png" media="(min-width: 800px)">
    <source srcset="logos/logo.png" media="(min-width: 600px)">
    <img src="default.png" alt="default picture">
</picture>
{% endhighlight %}

The above code shows how to use the `<picture>` element with the `media` attribute to show different images with the screen size is changed. More information about the `<picture>` element can be found on :link:[responsiveimages][pictureElement].

* :bell: The media queries
The last but not the least of the techniques for RWD is *media queries*. This is the technology fully standardized in CSS3. Basically you need to create media query listeners and define different media query rules. A simple example is as follows:

<% highlight css %>
@media screen and (min-width: 600px) {
    element {
        color: #f00;
    }   
}
@media screen and (min-width: 800px) {
    element {
        color: #00f;
    }   
}
{% endhighlight %}

When you design a web page today, you should always take *Responsive Design* into your mind. As different mobile intelligent terminals with screens are swarming around the world, this also bring the concept of *Mobile First*. So you design the web page for mobile:iphone: first and then using different *RWD* techniques to adapt the web page to larger screen sizes such as desktop screens:computer:, even TV screens:tv:.

[AListApart]: https://alistapart.com/
[960grids]: https://960.gs/
[bootstrap]: http://getbootstrap.com/
[pictureElement]: https://responsiveimages.org/
