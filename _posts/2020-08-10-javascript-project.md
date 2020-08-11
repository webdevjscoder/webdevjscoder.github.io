---
layout: post
title:  "JavaScript Project Week"
date:   2020-07-14 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

It was project week this past week...how was it you ask? Well let's just say it wasn't my best or proudest project at all.
It began great as many would want a project to begin but, if one puts their foot on the pedal its usually ideal to keep
it pressed until crossing the finish line. This wasn't the case for me and I completely regret it but as we all know we
keep moving on, improving along the way. With that being said, please don't be like me taking it lightly and believing
everything with come together magically. Once you learn something and you lay off of it for some time it begins to fade
away, its not fun having to revert back to learn it again. Its a waste a time. Anyhow, let me begin by explaining what
my application is about and how the functionality is suppose to work.

My project is based off of food creations before lets face it I am a food lover (I mean who isn't right?). I began with
brainstorming as usual with all projects, writing it down, visualizing how it will function is a great way to get
started and will likely speed up the development process. Using draw.io I began to diagram the backend for my app referencing
all the attributes that would be needed for each table. I only have two tables this go around, which was the minimum requirement,
for the `categories` table I went ahead and assigned a `name` attribute and for the `meals` table the same attribute of
`name` but for this table I decided it was belong to a `category` so I added a reference to the parent table by applying
a `category_id`. Using Rails as my backend API was a breeze to get up and built because lets face it Rails is nothing short
of second hand nature at this point.

After creating my backend API I began to explain to myself how I (a user) was going to be able to navigate or use my application.
I began by again diagramming myself a visual image of a couple of blocks with text inside explaining everything a user would
be able to do while using my application. Once I had that complete I than began to code and off I went, begin to fetch all
the categories I wanted to display on the screen. This project was a SPA (Single Page Application) which means the page
can have no refreshes and using DOM to render all the information on the page. This was not very difficult but then again
everything seems simple when one begins but once it gets started you begin to run into issues. Once I hit a bump I'd take
a crack at it and if no luck...I'd take a break and return to it again. After getting the fetch requests rendering, next
was allowing a user to create a new category.

Making a POST request to my backend could had happened in a couple of different ways. One, I could of made a fetch request
to the category url in this fashion:

```
    fetch("http://localhost:3000/categories", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        "Accept": "application/json"
      },
      body: JSON.stringify({
        name: "Mexican"
      })
    });
```

The other way was like the following:

```
    let formData = {
      name: "Mexican"
    };

    let configObj = {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        "Accept": "application/json"
      },
      body: JSON.stringify(formData)
    };

    fetch("http://localhost:3000/categories", configObj)
      .then(function(response) {
        return response.json();
      })
      .then(function(object) {
        console.log(object);
      });
```

Either way works and many can argue that one looks cleaner than the other but I used the second format. It is just out of
preference nothing to do with one being better than the other. `formData` is pretty obvious that is creating an object
from the body data, in this case for the information coming from the `form` that is being created. The `configObj` is
necessary in order to tell the `fetch request` to change from its default method `Get` to the `Post` method needs create
the new `category` a user is entering into the form. Once submitted its time for the backend to take over and create the
new instance. After that, it returns a `json` response that that we can `console.log();` in order to view the new information
being returned. We can then use that information to our liking, in my case I using it to create a new `category div` and
rendered it to the page for the user to see. Also, allowing the user to create a new meal, you can image it being exactly
the same to the category fetch request. Allowing the user to also delete a category and removing it from the page, this
was accomplished by creating a `fetch request` like the following:

```
function deleteCategory(categoryId) {
    fetch(`${http://localhost:3000}/${categoryId}`, {method: 'delete'})
          .then(function(response) {
            return response.json();
          })
          .then(function(object) {
            console.log(object);
          });
        }
```

This make a request to the specify category that the user wants to delete, once the backend finds the `ID` referenced it
deletes it from the database and it is no longer displayed in the browser. After, I get this all to work I begin to start
transferring the `fetch requests` to a separate file, for each model. The category and meal models both get their own file
that handles all the fetch request that allows me to create new instances through those files...which are referenced as
`classes`. Once that is done I can being to split the work from just the one `index.js` file. That completes the walk-through
of my app, like mentioned before it is by far the most disappointing project to date. But if I am being honest with myself,
I breezed by this section of the program and I regret it. I will make sure not to let this happen again but with that being
said I have a good understanding of the language but I could have a more in depth understanding. Which that will be a more
personal achievement at this point.