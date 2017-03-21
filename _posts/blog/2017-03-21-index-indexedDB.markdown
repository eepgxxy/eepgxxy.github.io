---
layout: post
title:  "What is Exactly index in indexedDB"
date:   2017-03-21 22:30:00 +0800
categories: blog
id: 24
---
Database has always been a *must have* in web development. It is usually located on the web server and using it is a required skill for back-end developers. Things have now changed, because front-end developers are now having a localized database called *indexedDB* in the browser side.

*indexedDB* is now the only recommended database standard by the *W3C*. *WebSQL* is only supported by some browsers, like Google Chrome. Knowing how to use *indexedDB* can bring front-end developers more possibilities when dealing with complex data in the client side, thus creating more diverse application scenarios. However, what is exactly *index* in the *indexedDB*.

Before digging into the ins and outs of *index*, we need to know the basics of how indexedDB works. *indexedDB* is a *window* object. It is a type of NoSQL database. This means, you can store JavaScript objects inside *indexedDB*.

To use *indexedDB*, you need first to create a database by the following code:

{% highlight javascript %}
var request = indexed.open("students", 1); 
//"students" is the database name and 1 is the version number of the database
{% endhighlight %}

Like SQL type databases, you then need to create a table and the different fields in the database. It is called `store` in *indexedDB*.

{% highlight javascript %}
request.onupgradeneeded = function() {
    var rq = this.result;
    var store = rq.createObjectStore("class1", {keyPath: "id"});
    //keyPath is primary key of the database
    store.createIndex("index1", "id", {unique: true});  
    store.createIndex("index2", "name", {unique: false});  
    store.createIndex("index3", "score", {unique: false});  
    //index of different fields are created for later query
};
{% endhighlight %}

From the above code we can see that the index of each field is created. This is used for later query as *query* is the most important function of a database. It is compulsory to put *index* as the first parameter of `createIndex()` method.

The *CRUD* operations of *indexDB* is easy. It is all about how to use the APIs.

{% highlight javascript %}
request.onsuccess = function() {
    var rq = this.result;
    var transaction = rq.transaction(["class1"], "readwrite");
    //create transaction of the object stores
    var store = transaction.objectStore("class");
    //fetch a particular store from the transaction
    store.add({id: 1, name: "xiaoming", score: 99});
    store.add({id: 2, name: "xiaohei", score: 89});
    //create records for the object store
    store.put({id: 2, name: "xiaohong", score: 100});
    //update a record in the object store  
    store.delete(2);  
    //delete a record by using the primary key
    var index = store.createIndex("index2");  
    //using index2 as the query criteria
    var cursor = index.openCursor();
    //open a cursor for search in the object store
    cursor.onsuccess = function() {
        var result = this.result;
        if(result) {
            var p = document.createElement("p");
            document.body.appendChild(p);
            p.innerHTML = "The result is " + result.value.id + 
                            " " + result.value.name + 
                            " " + result.value.score;
            result.continue();
        }
    };
};
{% endhighlight %}

It is already obvious that the *index* in *indexedDB* is a query tag for search. You must manually create them for later use. The *index* can also be clearly seen in the browser developer tools under the *Application* section for Google Chrome. It is of course in other browsers but the section name may be different.

