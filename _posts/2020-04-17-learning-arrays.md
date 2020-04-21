---
layout: post
title:  "Learning About Arrays"
date:   2020-04-17 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

**Array**

Today we are going to be learning about arrays, what they do, and why we need them in our code. Say for example we to
create a list of friends we want to hang out with, we can simply create a `variable` and  give a `value` with name of
our friend(s) so it would something like this:

{% highlight ruby %}
friend1 = "John"
friend2 = "Tommy"
friend3 = "Debra"
{% endhighlight %}

The code above doesn't look too bad because we can manage a small list of friends, but what if we decide, since you are
super popular to make a list of you 10 friends? Having to type out each and everyone of your friends with their own
`variable` and `value` would be a lot of work. Instead why wouldn't we just add the all together into one `variable` and
avoid all the extra work? So you can store a list of friends that would like the following:

{% highlight ruby %}
friends = ["John", "Tommy", "Debra", "Derek", "Eric", "Steven", "Jake", "Molly", "Chris", "Melissa" ]

puts friends
# prints
# ["John", "Tommy", "Debra", "Derek", "Eric", "Steven", "Jake", "Molly", "Chris", "Melissa" ]
{% endhighlight %}

Now does that look more manageable and a lot more cleaner? The code above has a `variable` named `friends` and is
setting it equal to a `value` that has `[]` brackets with the names of your friends in `""` double quotes, separated by
a `,` comma. Then we `puts` the `variable` `friends` which returns the array of friends we set as the `value`. The reason 
we use arrays instead of setting a `variable` and `value` for each friend is because we don't want repetitive code, we as 
coders are lazy. We want everything the easier way and it just so happens to be the cleanest way too (aren't we great).
There is many things that can be done with a collection of stored data, we can access, we can add, and we can change the
information that is stored within an array.

**The `.sort` Method**

Now that we got our feet wet and know what an array is, and why it's useful, let's talk about some very useful call methods
we can call upon to help us work arrays in our favor. The first method we are gonna cover is the `.sort` method, this
helps us by...you guessed it, by sorting our array, this means for `strings` they will be sorted alphabetically and
`integers` from smallest number to highest number. Below is an example of how `.sort` works:

{% highlight ruby %}
famous_cats = ["lil' bub", "grumpy cat", "maru"] # set our variable and value
famous_cats.sort # sort will sort the strings in alphabetical order
  => ["grumpy cat", "lil' bub", "maru"]  # returns original array unchanged
{% endhighlight %}

*Note: The return value of `famous_cats` remains unchanged and doesn't return the new array. Meaning calling `.sort`
won't necessarily return the new array value. If we were to call `famous_cats` it will return the original array 
["lil'bub", "grumpy cat", "maru"] not the sorted array.*

Since `sort` returns a new array but doesn't overwrite our previous array, we need to say a new variable to be able to
store the new array. This will result in two different set of arrays, which isn't bad you can keep them both.  If you 
don't care about the unsorted version of the array you can call `sort!`. This will sort the existing array and not have
to store the new array into a new variable. You'll notice the `!`. It's a ruby convention that a method with the `!` 
will do the operation in place. It will modify the receiver of the method (AKA the thing to the left of the dot).

**The `.reverse` Method**

The `.reverse` method simply reverses the array order:

{% highlight ruby %}
famous_athletes = ["Kobe", "Jordan", "LeBron"]
famous_athletes.reverse
  => ["LeBron", "Jordan", "Kobe"]
{% endhighlight %}

Similarly to `sort!`, you can call `reverse!`, again modifying the receiver of the method in place.

**The `.include?` Method**

This method will return a boolean of whether or not the array contains (or ​includes​) the element submitted to it 
inside the parentheses:

{% highlight ruby %}
famous_cats = ["lil' bub", "grumpy cat", "Maru"]
famous_cats.include?("Garfield")
  => false
famous_cats.include?("Maru")
  => true
{% endhighlight %}

Since we are just returning true or false, the receiver of the method, `famous_cats`, remains unchanged.

The **The `.first` Method**

This method will return the first element of the array, as its name suggests. Again, it does not change the return value 
of the original array.

{% highlight ruby %}
famous_cats = ["lil' bub", "grumpy cat", "Maru"]
famous_cats.first
  => "lil' bub"
{% endhighlight %}

**The `.last` Method**

This method will return the last element of the array, as its name suggests. Again, it does not change the original 
array.

{% highlight ruby %}
famous_cats = ["lil' bub", "grumpy cat", "Maru"]
famous_cats.last
  => "Maru"
{% endhighlight %}

**The `.size` Method**

This method will return the number of elements in the array.

{% highlight ruby %}
famous_cats = ["lil' bub", "grumpy cat", "Maru"]
famous_cats.size
  => 3
{% endhighlight %}

Even though arrays start with a 0 `index`, this method returns the actual number of elements, starting from 1.

*Note: Be aware that all of the methods we have covered in this reading are case sensitive. For example, `reverse` not 
`Reverse`.*
