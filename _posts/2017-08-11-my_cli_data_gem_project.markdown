---
layout: post
title:  "My CLI Data Gem Project "
date:   2017-08-11 17:02:26 -0400
---



I was very nervous to begin this project, as this was the first time that I wouldn't have the files and specs generated from the Learn environment. However, I was also very excited to build a program from scratch.

I decided early on that I wanted to scrape a news website, so I looked through some of the source code from the New York Times to understand how things were working. I found myself lost in the 'Food' section, so I figured might as well start with something I would actually like to read.  

After watching a few of the set-up videos on the learn.co platform, I set up my ruby gem and created the files I needed to begin the project. Getting all of the files working and the paths to appropriately connect took much longer to get the hang of than I expected. However, it was a very important exercise, since in the 'real world' all of these things will not be handed to me.

I decided it made the most sense to fill in some helper methods in my CLI class just to see that my program was running the way I wanted it to. I learned from one of the videos that starting with this class makes sense since this is how the user will interact with your program. As I began to run the program and test the CLI this made more and more sense to me.

I got my CLI worked out enough to be able to test out my program, so I moved over to my Scraper class to start scraping the 'Food' page of the NY Times. 

Thankfully, I really studied a lot of the source code before beginning this step, which made it easier to parse out later. 

Once I got my scraper code working (thank you binding.pry) I went back to my CLI class to put it all together. Here is where I struggled the most: my CLI wasn't pulling my scraped data into an array. Therefore, I couldn't have the user select which article they wanted to read.

After many hours of struggling and googling, I finally realized that I was scraping info but I wasn't 'doing anything with it.' I added my scrapped data into an array and this fixed many of my problems! 

```

    articles = [] # I originally didn't have this!


    doc.css('.story').each do |info| # or this 
      article = self.new
      article.headline = info.css("h3").text.strip
      article.author = info.css("h6.byline").text.strip
      article.summary = info.css("p.summary").text.strip
      article.url = info.css("a").attr("href").value
      articles << article # or this 
    end
    articles #or this 

    end
```

I worked through the rest of the CLI, allowing the user to pick an article and then geting the details, including a URL to read the entire article. 

The result is a very simple program but the journey getting there was very informative and necessary to becoming a better programmer. 
