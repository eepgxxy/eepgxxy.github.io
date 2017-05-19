---
layout: post
title:  "The Basics of Directives in Angular"
date:   2017-05-05 23:00:00 +0800
categories: blog
id: 39
---

*Directives* provide a variety of ways to abstract the HTML UI elements, attributes, classes, expressions and styles. There are tons of use cases in *Angular* for *Directives* which are described as follows:

* Directives for styles

{% highlight javascript %}
import {Directive, HostBinding, HostListener} from '@angular/core'

@Directive({
    selector: '[autoGrow]'
})

export class AutoGrowDirective {
    @HostBinding('style.width.px')
    width:number = 120;

    @HostListener('focus')
    onFocus() {
        this.width = 500;
    }

    @HostListener('blur')
    onBlur() {
        this.width = 120
    }
}
{% endhighlight %}

* Built-in Directives

There are many built-in directives in *Angular*. The frequently used ones are `*ngIf` and `*ngFor`.

The `*ngIf` is used for conditional expressions.

{% highlight javascript %}
@Component({
    selector: 'user',
    template: `
        <ul>
            <li *ngIf = 'show'>show or hide</li>
        </ul>
    `
})
{% endhighlight %}

The `*ngFor` is used for loops.

{% highlight javascript %}
@Component({
    selector: 'user',
    template: `
        <ul>
            <li *ngFor = 'let stu of students'>{{stu}}</li>
        </ul>
    `
})
{% endhighlight %}
