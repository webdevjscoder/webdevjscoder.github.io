---
layout: post
title:  "Intro to Rails"
date:   2020-06-07 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

Intro to Rails, before we get started, let's go through a brief introduction of how rails came to be. It all started back 
in 2004 when a man by the name David Heinemeier Hansson, a Dutch programmer was creating web applications with Ruby and 
noticed a significant pattern occurring, as he was just copying and pasting very common snippets of code from previous 
applications he built before. As many of us know a programmer love problem solving especially when they are difficult to 
accomplish. The rush is just so invigorating, that we have a love and hate relationship with coding (I’m sure many can 
relate), but the only way to solve issues like these is to step it up a notch to a higher level of abstraction. That is 
exactly what Heinemeier did, going on to develop what we know as Ruby on Rails.

With over a decade of open source contributions, Rails has evolved as one of the most powerful frameworks available. To 
fully grasp Rails we first have to know what Ruby on Rails actually is and what it’s not. It is a web framework, a web 
framework provides developers the tools they need in order to build applications. A good framework allows developers to 
have access to baseline tools such as routing, asset management, database connections, and the list goes on. This allows 
us not to have to create the baseline application functionality for each new project. Ruby on Rails is just a gem of Ruby 
code libraries, we have access to the <a href="https://github.com/rails/rails">open-source code</a> to be able to better 
understand how it works. It also uses the very popular MVC format which stands for Model-View-Controller that helps 
developers create the separation of concerns and organize their applications properly.

If you are still asking yourself why use a framework? Imagine you wanted to build something from scratch, let's go ahead 
use a gaming console for this example. You would first have  to start building the motherboard, the get it to actually 
make the console function before even being able to start creating the shell that will hold all the components in place. 
It would be a safe bet to say not everyone would have the patience to for that, so why not just invest in a gaming console 
that an organization that has already put in all the of research and development to create a professional system. This 
comes back around to answer the question about why use a framework, it would be possible to develop a site without it but 
the abstraction of the site would not be as efficient as a developed tool that has more than a decade's worth of information 
at our disposal.

What Ruby on Rails is not, a programming language, this the most common misconception. It is simply a set of code libraries
built in Ruby. It is also not a slow framework, in fact, it so straightforward that it can lead beginners to develop poor
coding practices. If built properly Rails can be as fast any other framework out there.

## Installing Rails

Now knowing this burst of information, we can go ahead and begin installing Rails on our computer via the command prompt
terminal. Go ahead and run the following command in the terminal of your computer:

```ruby
  gem install rails
```

Once the gem is installed you can create Rails applications. Depending on your system you may need to run `sudo` to
install the gem.

## Generate a New Rails APP

To create a new application run the following command in your terminal:

```ruby
  rails new <name-of-application> 
```

The common naming convention for Rails app names is usually lower case letters separated by '-', as shown in the above
example.

Now go ahead and change into the directory of the new Rails app:

```ruby
  cd <name-of-application>
```

## Create the Database

Before continuing lets go ahead and create the database by running:

```ruby
  rake db:create
```

## Start up the Rails Server

To start up the Rails server, make sure you are in the root of the application and run:

```ruby
  rails s
```

This command start up rails server (i.e s is short for server) and you should see the following 
output:

```ruby
  => Booting WEBrick
  => Rails 4.2.3 application starting in development on http://localhost:3000
  => Run `rails server -h` for more startup options
  => Ctrl-C to shutdown server
  [2015-11-14 22:16:54] INFO  WEBrick 1.3.1
  [2015-11-14 22:16:54] INFO  ruby 2.1.2 (2014-05-08) [x86_64-darwin13.0]
  [2015-11-14 22:16:54] INFO  WEBrick::HTTPServer#start: pid=3080 port=3000
``` 

To make the server is running properly go ahead and navigate over to `Http://localhost:3000/`. Here you see the message
"Yay! You're in Rails!", now you are able to start building you're application.

In order to showdown the server hit the button combination of `CTRL + C`.