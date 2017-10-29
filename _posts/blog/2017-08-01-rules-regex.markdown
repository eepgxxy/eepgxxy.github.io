---
layout: post
title:  "Knowing the Most Basic Rules of Regex"
date:   2017-08-01 23:00:00 +0800
categories: blog
id: 41
---

Regex or regular expression is the magic ward in every programming language inlcuding JavaScript. Knowing regex is the basic ability of any programmer and knowing regex well will distinguish you from other programmers.

The following are the most basic rules of regex while mostly can be applied to any programming language they are specifically for JavaScript.

* A regular expression matches the first occurrence of that character in the string

* Twelve metacharacters have special meanings
 the backslash \, the caret ^, the dollar sign $, the period or dot ., the vertical bar or pipe symbol |, the question mark ?, the asterisk or star *, the plus sign +, the opening parenthesis (, the closing parenthesis ), the opening square bracket [, and the opening curly brace {. 

* A "character class" matches only one out of several characters.

* Typing a caret after the opening square bracket negates the character class

* \w matches a "word character" (alphanumeric characters plus underscore)

* \s matches a whitespace character (includes tabs and line breaks)

* The dot matches a single character, except line break characters.

* \b matches at a word boundary. A word boundary is a position between a character that can be matched by \w and a character that cannot be matched by \w.

* The repetition operators or quantifiers are greedy and a ? after the repetition operators or quantifiers make them nongreedy.

* Non-capturing groups are made by adding ?: immediately after the opening parenthesis.

Regex is mostly used for operating strings in JavaScript。There are a few methods that are related to regex in JavaScript. Among those methods, *search*,*match* and *replace* are the most used regex related methods of *String* objects or literals. *test* and *exec* are the most used regex related methods of *RegExp* objects or literals.

* The *search* method

*search* returns the index of the first found matching character. 

{% highlight javascript %}
"hello world".search(/\s/);
{% endhighlight %}

* The *match* method

*match* returns the matching info as an object.

{% highlight javascript %}
"hello world".match(/\s/);
{% endhighlight %}

* The *replace* method

*replace* returns the string after replacement.

{% highlight javascript %}
"hello world".replace(/\s/, "@");
{% endhighlight %}

The more powerful feature of *replace* is that the second parameter can be a function. If the second parameter is a function, the function can also have a list of parameters, they are: the full text of the match; the captures of the match, one parameter for each;the index of the match within the original string;the source string.

{% highlight javascript %}
"border-bottom-width".replace(/-(\w)/g, function(all,capture){
    return capture.toUpperCase();
});
{% endhighlight %}

* The *test* method

*test* returns true when the regex match otherwise false.

{% highlight javascript %}
/\D/.test("hello world");
{% endhighlight %}

* The *exec* method

*exec* returns detail matching info as an object.

{% highlight javascript %}
/\D/.exec("hello world");
{% endhighlight %}

