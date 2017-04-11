---
layout: post
title:  "Bootstrap Your Website with Bootstrap"
date:   2017-04-11 21:00:00 +0800
categories: blog
id: 28
---
*Bootstrap* is one of the most popular front-end frameworks with responsive design being kept in mind. It may sound intimidating first, but it is in fact just a set of CSS classes and HTML elements that you use after including the necessary CSS files and JavaScript files:link:[Bootstrap][Bootstrap].

The good thing for *Bootstrap* is that it is actually very easy to use.
After downloading *Bootstrap*, you can see two folders: `css` and `js`(for bootstrap version 4). Since *Bootstrap* depends on *jQuery*, so you also need *jQuery* in order to use *Bootstrap*. As *Bootstrap* is going from version 3 to version 4, we are talking about version 4 in this post. The following code shows how you can bootstrap your web page using the *Bootstrap* framework.

{% highlight html %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>bootstrap</title>
    <link rel="stylesheet" href="css/bootstrap.min.css">
</head>
<body>
<script src="js/jquery.min.js"></script>
<script src="js/tether.min.js"></script>
<script src="js/bootstrap.min.js"></script>
</body>
</html>
{% endhighlight %}

The above code is the starter template for *Bootstrap* version 4. The main difference of the code above compared with that of version 3 are *added `viewport` meta tag* and *added `tether.min.js`*.

There are many styles, components and themes in *Bootstrap*. The one that you should know best is *grid* based layout for responsive design. The default grid layout is a 12-column based grid system. You can customize it to a different number of columns and different width for gutters etc.. Using it is as simple as adding the corresponding classes like follows:

{% highlight html %}
<div class="container">
    <div class="row">
        <div class="col-xs-4"></div>
        <div class="col-xs-8"></div>
    </div>
</div>
{% endhighlight %}

There are so many components in *Bootstrap* that we cannot describe them all within this one single post. Here I just give a typical `navbar` example as follows:

{% highlight html %}
<nav class="navbar navbar-toggleable-md navbar-light bg-faded">
  <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <a class="navbar-brand" href="#">Navbar</a>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="text" placeholder="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
{% endhighlight %}

Although you can use different components and styles provided by *Bootstrap*, you can also customize it using your own CSS styles or JavaScript codes to avoid your page looking like another page. So *Bootstrap* is really flexible.

As a front-end developer, you will use *Bootstrap* somewhere eventually. So getting used to *Bootstrap* is really important. And the only way to get professional with it is using it in your own projects.


[Bootstrap]: https://v4-alpha.getbootstrap.com/
