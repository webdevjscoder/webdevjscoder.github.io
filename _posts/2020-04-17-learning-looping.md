---
layout: post
title:  "Learning About Looping"
date:   2020-04-17 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

`#Loop`, `#while loop`, and `#until loop` as we learned in the previous blog post about `variables` and their `values` 
which remember we can make render anything we it to by simply calling the `variable`. Using these methods is to make 
our code more eloquent and reusable, we want to be able to say something without having to type it `"x"` amount of 
times, e.g. say you want to execute the following line of code:

{% highlight ruby %}
def greeting(name)
  puts "Hello, #{name}!"
end

greeting("John")
{% endhighlight %}
The code above is simply saying "Hey, I want you to take the name John and replace it in the placeholder of name" which
is called a `parameter` and the name "John" being called in the call function at the bottom is called an `argument`
that is what is being passed. That will execute `"Hello, John!"`, now say we want to render that 10 times...we have type
out `puts "Hello, #{name}!"` 10 times or call it 10 times. But, this is were the `#looping method` comes in to save the day
instead of typing it out 10 times, we create a method that does the work for us. We tell the method "Hey, I want you to
give me this phrase 10 times" it would look like the following:

{% highlight ruby %}
def greeting(name)
  10.times do
  puts "Hello, #{name}!"
  end
end

greeting("John")
{% endhighlight %}

Notice I used `"10.times"` (#looping), a `"do"` and `"end"` to create a `"block"`, inside the block I simply typed what 
I wanted it to render 10 times. Now I don't have to worry about typing it out 10 times manually the computer does it 
for me, all thanks to the `#looping method`.

The next method is the `#while loop`, this method will run through a block of code, which is set with `while` and `end`
keywords and go through your block of code "while" the condition is `true`. Once this loop hits the condition you set 
for it to meet, it will stop executing the code in the block. This means it will render what you set in between the 
`while` and `end` keywords, which would look something like this:

{% highlight ruby %}
counter = 0  # starting number
while counter < 10  # as long as counter number is less than 10 run
  puts "The current number is less than 10." # will print out 10 times
  counter += 1  # increments by 1 each loop around
end
# prints out 
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
> "The current number is less than 20."
{% endhighlight %}

Here, we set the `counter = 0` which is then passed into the the `#while loop` block for comparison, asking "Hey,
is 0 less than 20?" (which in this case it will be) "then go ahead and execute the block of code." This will continue
to run until the condition is no longer `true` and will break out of the loop and return what you put inside the block.

The last method we have is the `until loop` which is the inverse of a `while loop`. `Until` keyword will continue to
execute as long as the condition returns `false`. A way of thinking about the `until` is to remember it as "if not".

{% highlight ruby %}
counter = 0
until counter == 10
  puts "The current number is less than 10."
  counter += 1
end
# prints
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
> "The current number is less than 10."
{% endhighlight %}

We are setting `counter = 0` once more but this time we are running it in the `#until loop`, which is asking "Hey, is
0 equal to 10? "If not" run the block of code, increment by 1 and repeat until it returns `true` then break out."