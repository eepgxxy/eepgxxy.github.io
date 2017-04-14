---
layout: post
title:  "Ajax is Indispensible"
date:   2017-04-14 23:00:00 +0800
categories: blog
id: 29
---
*Ajax(Asynchronous JavaScript and XML)* is already an indispensible technology in web development nowadays. The reason is obvious: it is the most used technology in SPAs (Single Page Applications). Because of SPAs, you have the similar experiences when visiting web pages just like using your desktop applications. Information on the website are being shown and hidden in a more natural way compared with the old style web pages.

So how to use Ajax using plain JavaScript? The following steps are needed:

* Creating an XMLHTTPRequest object

All the magic behind *Ajax* are contained in the *XMLHTTPRequest* object. When you initiate such an object. You are free to use all the essential properties and methods of the object.

{% highlight javascript %}
var request = new XMLHTTPRequest();
{% endhighlight %}

* Accessing the file on the server

Ajax is originally designed to access the XML files and that is where its name is derived from. However, Ajax can also be used to access other types of files, like `.txt`, `.html`, `.json` and other types of files nowadays. So there are two kinds of properties of the *XMLHTTPRequest* object for this purpose: `responseXML` and `responseText`.

{% highlight javascript %}
request.open("GET", "text.xml");
request.onreadystatechange = function() {
  if(request.readyState === 4 && request.status === 200) {
    var text = request.responseXML;
  }
}
{% endhighlight %}

There are five different *states* for the communication between browser and server using *Ajax*: `0`, `1`, `2`, `3` and `4`. The different *states* are standing for the different stages of the communication. And `4` is the final stage which means all the information required by *Ajax* successfully arrive at the browser from the server. The code `200` is the successful symbol for HTTP transmission protocol.

* Sending the *Ajax* request

This part is just like pressing the *engine start* button to start your car. So you send the *Ajax* request to start the whole *Ajax* communication life cycle in this way.

{% highlight javascript %}
request.send();
{% endhighlight %}

You can also send parameters during this stage by putting the parametersrs inside the `send()` method.

{% highlight javascript %}
request.send(data);
{% endhighlight %}

With just three steps, your old sluggish website can turn to be modern agile website:wink:.

You can also improve your *Ajax* workflow by using *jQuery* like follows:
{% highlight javascript %}
$.ajax({
  url: '/path/to/file',
  type: 'default GET (Other values: POST)',
  dataType: 'default: Intelligent Guess (Other values: xml, json, script, or html)',
  data: {param1: 'value1'},
})
.done(function() {
  console.log("success");
})
.fail(function() {
  console.log("error");
})
.always(function() {
  console.log("complete");
});
{% endhighlight %}

