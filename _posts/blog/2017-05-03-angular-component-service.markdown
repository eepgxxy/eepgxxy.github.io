---
layout: post
title:  "Mastering Component and Services in Angular"
date:   2017-05-03 23:00:00 +0800
categories: blog
id: 37
---

*Component* is the key concept in *Angular*. It is an UI class with *selectors*, *template*, and other metadatas. It is the main way in *Angular* to build and specify elements and logic on the page. You can reuse it across your apps. Your whole app can be regarded as a tree of components as illustrated in the following figure:point_down:.

![Component Tree](/images/component-tree.jpg)

*Service* works similarly in *Angular* as in *AngularJS* except that it is a class. It is used for reusable data to share between components throughout an application. Services in *Angular* are inheritely asynchronous. This means that the data can be returned as a promise or as an observable using *RxJS*.The steps of creating and using a component and a service are as follows:

* Creating a component

{% highlight javascript %}
import {Component} from '@angular/core'

@Component({
    selector: 'stu',
    template: '<h1>hello {{name}}</h1>'
})

export class StuComponent {
    name: string = "xiaoming";
}
{% endhighlight %}

* Creating a service

{% highlight javascript %}
export class StuService {
    getStuInfo(): string {
        return "xiaohong";
    }
}
{% endhighlight %}

* Using the service in the component

The last step is to modify the *component* in order to use the service being created.

{% highlight javascript %}
import {Component} from '@angular/core'
import {StuService} from './stu.service'

@Component({
    selector: 'stu',
    template: '<h1>hello {{name}}</h1>',
    providers: [StuService]
})

export class StuComponent {
    name;
    constructor(stuService: StuService) {
        this.name = stuService.getStuInfo();
    }
}
{% endhighlight %}


