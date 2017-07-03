---
layout: post
title:  "Getting Specific with CSS Selectors "
date:   2017-07-03 23:33:19 +0000
---


Maybe a lot has changed in the past few years (probably not), or maybe I wasn't paying enough attention in my college web development class (probably), but I don't remember being able to get so specific with my CSS selectors - and well, it's pretty cool. 

A CSS selector is the part of a CSS rule set that allows you to be very specific about where you want to style your HTML. 

There are a bunch of different selectors available, all to make your website look absolutely beautiful. Let's see how specific we can get. 

There are simple selectors, combination selectors, attribute selectors, parent, child, grandchild selectors - all allowing you to style down to the smallest detail.

Starting broad are our simple selectors. These match one or more elements based on element type, class, or ID.

**Example 1:** Here I am styling the ID of 'wall'. I'm giving it a position, margin, image, size, shadow, border. I'll give you a moment to ooo and ahh, but this is pretty simple example of how to style a basic element. 

```
#wall {
  position: relative;
  margin: 40px auto;
  width: 980px;
  height: 622px;
  background: url(../images/wall.jpg) no-repeat center;
  -moz-box-shadow: 15px 15px 47px lime, -15px -15px 47px aqua;
  -webkit-box-shadow: 15px 15px 47px lime, -15px -15px 47px aqua;
  box-shadow: 15px 15px 47px lime, -15px -15px 47px aqua;
  border: 15px solid white;
  border-bottom: 60px solid white;
}
```

Getting more specific are **combination selectors.** Here we can combine two or more selectors together.

**Example 2:** Below I have styled the class of 'tag-1' inside the ID of 'wall.'

```
#wall .tag-1 {
  background: url(../images/tag-1.png) no-repeat;
  z-index: 7;
  display: none;
}
```

Getting even more specific are **child combinations**. This is a selector that only targets immediate child elements. 

**Example 3:**  Here I have styled only the first class of 'box' under the class of 'tag-1.' This would come in handy if I wanted to add some fancy styles to the first box, but not to any of the others in the 'tag-1' class.

```
.tag-1 > .box {
   float: left;
   padding-bottom: 15px;
}
```

One of my other personal favorite selectors are **psuedo-selectors**, which allow your link to have some style in all stages of link behavior (hover, click, active, visited etc) 

Example 4: Here are are my styles in all stages of link-dom. 

```
**(link and visited)**
#details a:link, #details a:visited  {
  color: black;
  text-decoration: none;
}

**(hovered)**
#details a:hover {
  color:black;
  text-decoration: underline;
}

**(active)**
#details a:active {
  color:red;
}

```


There are a lot more to choose from: universal selectors, multiple selectors, parent and sibliging selectors...maybe one day aunt and uncle, but I think you get the point. Also, I found this nifty [cheat sheet](http://www.cheetyr.com/css-selectors) since the internet is magical place! 

Now back to selecting my selectors...


