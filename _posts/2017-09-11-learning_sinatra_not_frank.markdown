---
layout: post
title:  "Learning Sinatra (Not Frank)"
date:   2017-09-11 19:13:09 +0000
---



After wrapping up the Ruby Data Gem CLI project, I was excited to begin learning something brand new with SQL, ActiveRecord, ORM's etc - but for the most part the learning of that was pretty boring (but important)... With an understanding of its future value, I navigated that portion of the course as best I could, as I know it will creep back in later. (It always does)

I'm ready now to become a 'maker on the web' by jumping into Sinatra. I always wondered how dynamic web apps were made (and how they looked so pretty). Learning about .erb files was eye-opening.

What are .erb files? 'erb' stands for "Embedded RuBy". An .erb file is HTML with Ruby code embedded in. Sinatra will evaluate the Ruby to add content to the file dynamically, and will output an HTML file for rendering. 

In .erb files you can also write JavaScript but thus far I've only been using Ruby in HTML. 

Here's an example in which I want my web app to render the date: 

```
<html>
<h1>Today</h1>
<%= @time = Time.now %>
<p>The date is <%= @time.strftime("%A, %B %d, %Y") %></p>
</html>
```

Everything inside the <% ... %>  tags is Ruby code and everything outside of them is HTML. The results of the Ruby code will be embedded whenever the ERB tag also has an equals sign: <%= ... %>.

While I still have a long way to go, it's great to start seeing different languages combine and create some really awesome things.  
