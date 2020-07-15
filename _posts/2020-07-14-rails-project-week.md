---
layout: post
title:  "Rails Project Week"
date:   2020-07-14 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

This week's project was to build a Ruby on Rails web app...didn't take a week to finish though. Idk if it was the break
we got that got me thinking that I had the time to slack off but, turned out to be a horrible idea as my porject turned
out to be a little more difficult than I thought. Even though I had some signs that this project wasn't like the others,
it all began when I was attempting to connect my postgres database to rails. That itself took me about two days to figure
out, I really need to learn how to reach out for help when I need it. Not saying I didn't because I did...but my instructor
is not familiar with windows, so he directed me to a cohort member. He seemed like he was ready to help with the issue
than he just disappear so again I was alone to deal with it. So, I did.  It took me breaking my WSL terminal to figure out
how to configure my postgres database to my application. Needless to say, I finally was able to get my project up and
running. I began to build the entire backend of my app, I created my migration for users and vehicles. Having to use a
CSV file to seed my database turned out to be a blessing. I was able to make the connections necessary to get my vehicles
rendered in my views. For vehicles alone I used about 7-8 tables.

After creating all database tables and components, I began to create the users table because lets face it...an application
is not an application if we don't have users to use it. Once I got the table built like the image above, I used a simple
validation to validate the user when they log in. A simple `validates :email, presence: true` and `validates :email, 
uniqueness: true`, you might be wondering why didn't he just set them on the same line. There is a reason for that, as I
changed my `presence: true` to `presence: {message: 'email is already taken.'}` for a user to receive an error when they
try to create an account with the same email (same goes for the validating an email). The separation was simply for separation
of concerns in a very minimal way. After validating a user, I began to create the connections between a user and a vehicle,
using a joins table for many-to-many relationship. A user can have many vehicles and a vehicle can have many users, this
is were the user_vehicles table comes in. Since in Ruby we use convention over configuration, I named the joins table after
the tables I wanted to have a many-to-many relationship, giving a user many vehicles through user_vehicles and vice versa.
Once I got that relationship going I was able then display a users vehicles by calling user.vehicles and I would get a
`CollectionProxy:[]` with the vehicles associated with that specific user. Same went for the vehicle, I could call
vehicle.users and get the users associated to that instance.

Making these associations made it insanely easy to call on different ActiveRecord objects and display the information in
the views, without making call to the database every time I need a piece of information from a model. One of the most
difficult things I came across was being about to update or delete an object. To specify when I was rendering the show page
for a vehicle I used something like `@vehicle.car_make.name` to display the make of a vehicle but, then I used 
`@vehicle.inventories[0].price` to display the price of a vehicle (used [0] to call the first index of the array). I got
to work fine and all was great until I came across updating and deleting the vehicle from the database, I ran into an issue,
I had to delete the children from the database as well...so how did I do this? Well luckily, activerecord has method just for
the occasion is called `:dependent => :delete_all` or `:dependent => :destroy` that is added to the `has_many` associations
that you would like to delete once the parent is deleted (`parent < child < grandchild`). Once I got that working I was
able to proceed without a hitch...until again I got to another issue but of course it was resolved no other way around it.

Once it was all done I was able to focus on the front-end of the site and really start adding some life to the skeleton I
had. I went the difficult way and did all my css styling by hand with no help any styling libraries because I believe in
learning everything there is to know about before using anything that will instantly create something for me. This way if
I one day do decide to use something like a `bootstrap` library, I will be able to debug the issue without a problem and
I feel like I would definitely be able to. Don't get me wrong I'm no css master or even a great web designer but I can
put something together to make it look decent enough. I wish I had the eye for design but I of course don't but that okay
because I am learn along the way. Continuing to learn everyday, whether its using a new database, language, or even rendering
a div in the correct spot...its all a positive to me. Finishing the css I than create a very simple search form so that a
user could find a vehicle by its car make, it took me a while to finally realize how to make call to the database to get
select make and render all the matching vehicles. First, I had to make a call the `CarMake` model and look for the car make
by name and grab that `id` then pass that `id` to another action to search the `Vehicle` model to find the vehicles that
matched with that `id`. Finally, I was able to render the information for the vehicles I needed and was able to present
the user with correct data. Also, created custom `scopes` to categorize the vehicles by price.

Finishing this project was a must and I did, now that I'm done I feel like I can build it in within day instead of weeks,
but like with every project who doesn't feel like this? So that being said I feel like I just slacked off too much on this
one and that is a big regret for me because I could of used that wasted time to add more to my project. But like everything
we live and we learn, now I know if I have a vacation, pretend there isn't one that was my mistake but, one that can be
corrected. My experience with the project was amazing overall getting to use such a powerful framework like Rails was an
honor and very advance for beginner Rubist. For one that has his far share it was a incredible to see the educated guess
Ruby on Rails makes for us and that is something to not take for granted, because even though it does all of work for us.
Its easy to get use to and forget how to manually create forms or routes, or even a simple button tag. Moving forward with
rails I will be using it more but also using custom: forms and routes, here and there.