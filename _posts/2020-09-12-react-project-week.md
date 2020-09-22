---
layout: post
title:  "React And Redux Project Week"
date:   2020-09-19 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

![React Logo In Hand](https://miro.medium.com/max/700/1*EVqCcmCPgpNKxU1wzcTHgw.png)


In this blog I will be talking about my React project, my thought process, reason behind it, and experience. When I first
heard of React I had no idea what to expect, I have previously meddled with React but in all honesty, I didn't realize
what it was and how powerful it could be, when utilized properly. This is were Flatiron came in and gave me a hand with
to fully understand the true power and purpose of React.

Even though I now have knowledge of the language and all its perks, I still don't truly understand it. But I will say 
this, I was mesmerized by how clean and simple it looked, when everything was broken down into separate files call 
`components`. It was simple to grasp at first, and thinking about it now it still sounds simple, breaking down a file 
into separate `components` and importing them into the file you wish to render them in. Sounds simple enough right?
 
Well it was but that's not really the confusion I ran into, the main issue I had was when I ran into `container components`. 
This was when I began to struggle a bit. I think the main reason was because I began to overthink the logic, which is a 
weakness of mine, overthink. After reading a blog by Dan Abramov it became clearer what a `container component` was and
how they operated. `Container components` are concerned how things work and usually are stateful, as they tend to provide
data sources. He also mentioned `presentational components` which I was already familiar with, but didn't hurt to polish
what I already knew. Which is that a `presentational component` is more concerned about how things look than any actual
logic.

Once I got this down, I was able to start building mapping out my application. First, I began with brainstorming it by
draw a diagram of how the relationship would look and connect with each other.

![Diagram](/assests/relationship-diagram.png)

Once I had this done, I began creating my backend using Rails Api. Doing so would allow me to request data from the frontend
as well as send requests to the backend to persist data being posted by a user. Going this step, I realized that my tables
were not connecting properly and I decide to go in a different route and reconstructed my relationships.

![New Diagram](/assests/new-diagram.png)

Deciding to shorten my tables and simplify them for those complicated unnecessary tables. Now I had everything to begin
building out my frontend. This is were React and Redux come into play, initially creating my application with the command
`npx create-react-app my-app`, of course I replaced my my-app with my own app name. This created a base structured
application for me, I than `npm start` to begin the react server.

![React default page](https://scotch-res.cloudinary.com/image/upload/v1541947988/dprot2efxxjkbyijqymh.png)

I replaced this page with a `Hello World` message imported from a hello component I created in order to see if the
application was working properly. This step is not necessary as its just my preference, from here I constructed all my
components in a directory named `components`, because it conventional to place all components in a this folder. I also
created a directory named `containers` this is where all the `container components` live. After all this was in place and
I had some logic for my application, I then utilized Redux. From redux I imported `create store`, which takes in an argument,
a `reducer`. A reducer is which we can initialize a store object which and can be empty like so: `reducer(store={})` or 
`reducer(store={ users: []})`. It can be structured as needed but once that it is done, we have to add the second argument
to the reducer because the way a reducer knows what to do with the store is by `actions`. Actions are needed to provide
instructions on what to do with the store object, whether its to remove or add items from the store. We then finally
import the last very important key from redux, its the `Provider` which is used to wrap the `<App />` component in the
index.js file as so:

![Redux provider](https://miro.medium.com/max/508/1*GwPYBaQTTBVMK-v-clUjDA.png)


This is necessary because after we do this, we can then pass the store variable into provider as a `prop` this allows
access to all the components in my application, creating what is called a `global store'.

Enters Redux Thunk, we use redux thunk for organization purposes. This allows us to separate actions and combine reducers
together. This is called `combined reducers` were we import all the reducers that are necessary for an application. This
might seem like an overkill for a small application but once it becomes larger, this will be a lifesaver. That was all I
needed to complete my app, its a not easy but once you began and keep at it, it becomes natural take my word for it. Now
I am completely comfortable with React and Redux, and can't wait to create future applications. 

![That's all folks](https://i.pinimg.com/originals/4e/9e/6f/4e9e6f979347906a426adcbe57fd3259.gif)