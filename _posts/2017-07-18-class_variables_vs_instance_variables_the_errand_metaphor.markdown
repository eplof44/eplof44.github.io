---
layout: post
title:  "Class Variables vs. Instance Variables (my errand metaphor)"
date:   2017-07-18 11:55:30 -0400
---


In order to wrap my mind around object orientation, I have been thinking a lot about programming in terms of metaphors. This has been particularly helpful when trying to distinguish between class variables and instance variables.

Let’s start by just recognizing the syntax of both types of variables. The ‘@@’ indicates a class variable and a single ‘@’ is an instance variable. But what really is the difference?

Enter the metaphor. I’ve been thinking of an entire class as a day of running errands and each instance of the class is me stopping at a different store. 

```
class Errands 

@@all_items = []  #class variable 

@target_items = [] #instance variable 

end 

```

Class variables are shared among the class and all instances of the class.

Instance variables are not shared by all instances of the class. They are local to a specific instance. 

If I went to Target, the grocery store, and the pharmacy (which let’s be real, I would never need to do if I went to a Target) the entire @@all_items array would know about all of my purchases, but I could also access just the items purchased at Target through the @target_items instance variable. 

I could even add another class with a different list of errands and return them all from my @@all_items array. 
So, if I wanted to know what I purchased after the entire shopping trip, I would want to access @@all_items.  If I just wanted to know what I got at Target I would want to access @target_items. 

Now it of course gets more complicated than this, but I’ve found this to be a digestible way of understanding how I need to keep track when building a program. 

