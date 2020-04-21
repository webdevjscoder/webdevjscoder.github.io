---
layout: post
title:  "First Day of My FlatIron Course!"
date:   2020-04-13 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

My first day beginning my course with FlatIron...what can I say? The leaders of my cohort are just amazing and I can't 
wait to continue the course with them, I am so excited! I gave myself a headache. On my first day we had orientation to 
meet the team that will be leading us to a successful and fulfilled programming career, I cannot begin to brag about 
how much they were involved with us as students it's incredible. Anyways, today's assignments for me were the following: 
Variables and Methods, which helped me understand what a variable and method were. A variable is a basically a container 
of food that one puts their food in and stores it, that variable is assigned a value which is food stored inside. It 
looks something like this:

{% highlight ruby %}
# string
box = "pizza"
puts box      # prints "pizza"
{% endhighlight %}

The (container) -> `box = "pizza"` <- (food) it also be something like this: `grocery = "eggs"`...there is no limit 
(there is actually) what you can name a variable and the value you pass it. The values we pass in to a variable can be 
a range of things like a string `"this is a string"`, an `integer (5)`, `booleans`(`true` or `false`), etc. When I say there is 
actually a limit I mean you can't use keywords like: `end`, `super`, `method`, etc. these are reserved keywords that Ruby 
uses, so therefore, they can't used as variables. It's also good practice to always use lowercase letters when 
naming a `variable` and use `snake_case` when naming a variable as well. Now on to a method, a method is basically...a box 
too, just like a `variable` but this box is unique. When I say unique think of a magician that pull a card out of thin 
air, just like the magician a method can pull out anything on the box you please; for example:

{% highlight ruby %}
def greeting   # method statement
    puts "Hello, guys!"   # method box
end   # closes method

greeting   # calls (renders) method
# prints "Hello, guys!"
{% endhighlight %}
 
Now there is something more special to this method than meets the eye, if you pass in something called a `parameter` 
this will store a placeholder for whatever you wanna call in that method later, like this:

{% highlight ruby %}
def greeting(name)          # method statement with an parameter (name)
    puts "Hello, #{name}!"  # method box, note ${this} is called interpolation
end  # closes method        # same as "" + name + ""

greeting("John")   # prints "Hello, John!"
                   # note "John" is the argument and 
                   # needs to passed in order for greeting to print
{% endhighlight %}

These can take as many `parameters` as needed but make sure to name them as specific as possible for others to be able to 
read your code later or even yourself, after a long time of not looking at your own code, you'll forget what its 
function was for. A `boolean` is a way to identify if a statement is `true` or `false`, this can be used inside of a method. 
`Booleans` are simple to identify, they are either `true` ("truthy") or `false` ("falsey"). Take a look at the example
below:

{% highlight ruby %}
# boolean
question = true    # "true"

nil   # "false"
{% endhighlight %}

`Logic` and `Conditionals` are what use booleans to provide them with necessary information to define if something is 
`true` or `false`, syntax goes as followed: 

{% highlight ruby %}
if 5 > 2
    print "5 is greater than 2"  # should print this because its true
else
    print "5 is not greater than 2"
end
{% endhighlight %}


`if` something is `true` then return `true` else return `false` that simple, (not really) but you get point. There is 
also another way to use a `Conditional Statement` and that is using the `if`, `elsif`, and `else` method, which allows 
you to pass in multiple statements:

{% highlight ruby %}
if 2 > 5
    print "2 is greater than 5"
elsif
   print "2 is not greater than 5"  # should print this because its false
else
   print "This is all wrong."
end
{% endhighlight %}

`Ternary Operations` are a shorter way of calling a Logic and Conditional statement as followed: 

{% highlight ruby %}
# ternary operator
age = 1

age < 2 ? "baby" : "not a baby"   # this is the same as example above
# prints "baby"
{% endhighlight %}

Is age less than 2? if (true) return `baby` : else return `not a baby` (false), but it's good practice to only use with
`if` `else` statements and not `if`, `elsif`, and `else`. Case Statements are used when you have to many `elsif` 
statements which example will be provided below:

{% highlight ruby %}
name = "John"

case name
    when "Alice"
       puts "Hello, Alice!"
    when "John"
       puts "Hello, John"   # prints "Hello, John"
    when "Janice"
       puts "Hello, Janice"
    else
       puts "Who is this?"
end
{% endhighlight %}

**More Examples:**

**Variables**

{% highlight ruby %}
# string
toy = "Woody"
puts toy      # prints "Woody"

# number or integer
number = 5
puts number    # prints "5"

# boolean
question = true    # "true"

nil   # "false"
{% endhighlight %}

**Arrays**
 
{% highlight ruby %}
names = ["John", "Sid", "Tom"]

puts names    # prints ["John", "Sid", "Tom"]
{% endhighlight %}

**Methods**

{% highlight ruby %}
def greeting   # method statement
    puts "Hello, guys!"   # method box
end   # closes method

greeting   # calls (renders) method
# prints "Hello, guys!"
{% endhighlight %}

**Methods with parameter**

{% highlight ruby %}
def greeting(name)          # method statement with an parameter (name)
    puts "Hello, #{name}!"  # method box, note ${this} is called interpolation
end  # closes method        # same as "" + name + ""

greeting("John")   # prints "Hello, John!"
                   # note "John" is the argument and 
                   # needs to passed in order for greeting to print
{% endhighlight %}

**Method scope**

{% highlight ruby %}
name = "Joe"   # method scope

def greeting(name)
    puts "Hello, #{name}"
end

greeting("Jacob")  # prints "Hello, Jacob"
# this argument is within the method so name is 
# again used but not with the value of "Joe"
{% endhighlight %}

**Using method scope**

{% highlight ruby %}
programmer = "Brian"   # method scope

def greeting(programmer)  # we pass in name as a parameter
    puts "Now #{programmer} can be used."
end

greeting(programmer)   # now we can use it
# prints "Now Brian can be used."

# Accessing a local scope (which is located inside a method)  is not possible
# only global scopes can be called into a method
{% endhighlight %}

**Puts and Prints**

{% highlight ruby %}
3.times { print "Hello!" }
#  > Hello!Hello!Hello!

3.times { puts "Hello!" }
# > Hello!
# > Hello!
# > Hello!

Puts "Hello World!" # returns nil because there is no return being passed in
"Hello World!"  # returns "Hello World!"
{% endhighlight %}

**Boolean**

{% highlight ruby %}
def return_true
   7 < 10
end
# returns "true"

def return_false
   8 > 10
end
# returns "false"
{% endhighlight %}

**Ternary Operator**

{% highlight ruby %}
age = 1

if age < 2
    "baby"
else
   "not a baby"
end
# returns "baby"

# ternary operator

age = 1

age < 2 ? "baby" : "not a baby"   # this is the same as example above
# prints "baby"
{% endhighlight %}

**If Statements**

{% highlight ruby %}
if 5 > 2
    print "5 is greater than 2"  # should print this because its true
else
    print "5 is not greater than 2"
end

if 2 > 5
    print "2 is greater than 5"
elsif
   print "2 is not greater than 5"  # should print this because its false
else
   print "This is all wrong."
end
{% endhighlight %}

**Case Statements**

{% highlight ruby %}
name = "John"

case name
    when "Alice"
       puts "Hello, Alice!"
    when "John"
       puts "Hello, John"   # prints "Hello, John"
    when "Janice"
       puts "Hello, Janice"
    else
       puts "Who is this?"
end
{% endhighlight %}