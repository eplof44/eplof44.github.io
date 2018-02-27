---
layout: post
title:      "My Rails App - BackPacker"
date:       2018-02-27 01:06:24 +0000
permalink:  my_rails_app_-_backpacker
---


My Rails project, BackPacker, is an app that allows you to keep track of your camping trips and all of the items you are bringing with you on the trip. A user is able to create a trip, create items, and then also associate those created items with a trip, or create items on the fly when creating the trip.

Before I got to work building out my migrations and models I went back through my labs as a refresher and then mapped out, on paper, how I wanted the different models to interact. The blueprint of how I wanted my app to work was essential to building and organizing my work-flow.

The rails project really highlighted for me how important it is to create your own projects from scratch. There is no better way to learn than debugging your code and then using the power of Google to research your issue. There is also no greater satisfaction than when it finally works.

I had a few challenges along the way. The first was with implementing my Omni-auth with Facebook. Somewhere along the way, I decided I would rather have people log-in with their Google account, but I already had the Facebook keys in my app. It took some back and forth to get this working but once I did I was very proud of myself. While the implementation of the Google log-in is not so dramatically different from the Facebook (which we did the lab on) it did require a few additional lines of code.

Another challenge I faced was getting all of the items created by the user to populate in the form for creating a trip. The collection boxes originally showed all items created by all users, but I only wanted the items created by the current user. In hindsight this was a ‘silly’ mistake and a switch from Items.all to current_user.items fixed it immediately.

I also implemented a class method in Items using an ActiveRecord SQL query where the list of camping trip gear would suggest an item to remove from your bag. When a user creates an item, they also assign it a weight and value. If the weight of the item is greater than 10 lbs and the value is less than 3, the app suggests not packing it.

While challenging, I actually had a lot of fun creating my rails portfolio project and seeing my knowledge come to life. There is a lot that can be added to improve the app and I look forward to building it out more over time as my skills improve.


