---
layout: post
title: "The Session and Application Objects in JSP"
date: 2015-12-01 21:17:17 +0800
categories: blog
---

HTTP is a stateless protocol, which makes it difficult to share data between different user requests. The JSP objects **session** and **application** thus come to compensate the so-called drawbacks of HTTP.

Sessions are used to maintain state between one request and the next. Normally the following four ways can expire a session:

* :bell: The web server is shutdown.
* :bell: The session has timed out.
* :bell: The browser is closed. 
* :bell: The session is removed intentionally.

The most useful session methods are `session.getAttribute()` and `session.setAttribute()`. The two methods can be used to store the data for use between different user request pages. Data are stored in session as `Object` data type. Thus conversion to needed data types is necessary when `session.getAttribute()` is used. Shopping-cart scenario is a classic application area for session object.

In some cases, session ID is used by programmers to distinguish between different user browser requests. The method for this is `session.getId()`.

Application is another JSP object to maintain the state between different user requests. However, as an global level object, it is used to store data between different users' requests and can only be expired when the web server is shutdown or the application is removed intentionally.

Same as sessions, `application.getAttribute()` and `application.setAttribute()` are the two most used methods. Visitors' count and shared message board are the typical scenarios for application object.

More infomation can be obtained from the same book :book: [Professional Java for Web Applications][jsp-book] by *Nicholas S. Williams*.

[jsp-book]: http://www.wrox.com
