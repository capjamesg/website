---
layout: post
categories: ["Web", "Post"]
title: "Writing a New Tab Extension: Part II"
---

I have been writing my own new tab extension for Firefox. I thought I was done yesterday but I decided to make a few enhancements. I didn't end up implementing any of the "fluff" features that I had in mind, like the ability to edit links on the new tab page. I did have two itches that I wanted to scratch.

I find that in the haste to think of a new project idea it's easy to skip over the post-development changes that make all the difference. On this website, most of what you see is the result of small, continuous changes. My birthday announcement (yes, it's my birthday!) was added a few days ago as a countdown. Now it displays my birthday. I wrote this by hand. There is no back-end code that automatically changes the announcement. My blog feed has evolved from a list of posts into a full micropub feed back into a list of posts.

## Fun Holidays

I had an urge to add a "fun fact" feature to my new tab page. This is in the same spirit as the new quote that appears on the page every day. I wanted something else to look at in the morning while I am setting up my computer. The new quote feature is nice. It's designed to inspire me to keep going. It will probably not make me laugh. Because I like to laugh, I decided that I would display a "fun holiday" on the new tab.

This feature involved some front-end and back-end development. I started by looking for a source of fun holidays. I could not find an API that would let me retrieve a fun holiday for a particular date. There are plenty of websites out there that display this information. I just couldn't access it programmatically. I did not let this minor hiccup deter me from my goal to display fun holidays on my website.

I decided that I would write a simple web scraper script that parsed the fun holidays data from the Time and Date website and put it into a JSON file. I could then use this JSON file to retrieve the "fun holiday" of the day. 

The scraping script I used retrieves all of the cells in Time and Date's fun holiday table. I go through each column and find the day of a holiday as well as the name of the holiday that occurs on that day. I add these values to a dictionary. Here is an example entry:

```
"01/10": ["Thursday", "International Coffee Day"]
```

I did want to remove the day of the week but I did not have the time to remove it. Interestingly, Time and Date shows multiple holidays for some days. Today, October 1st, is not only my birthday and International Coffee Day, but it is also "no rhyme or reason day." I'll talk about why I know this in a minute. I looked at the Time and Date site and it appears as if the most important fun holiday of the year, International Coffee Day, appears first.

I changed my Python script so that it would only save the first fun holiday for any particular day to the dictionary. This saved my script from overriding existing entries where multiple fun holidays were present for a particular day. I save this data to a file called `days_of_year.json` that exists on my website. [Click here to view the final output of my program](https://jamesg.blog/assets/days_of_year.json). My Python script to collect fun holidays is part of my blog because I save the file to my blog.

## No Rhyme or Reason Day

Should I take it as a sign that today is also no rhyme or reason day? I think I'm reading too far into it. The reason (no pun intended) that I know today is no rhyme or reason day is that my Python script initially overwrote the first entries for any days with more than one fun holiday. This meant that International Coffee Day, which appeared first on Time and Date's table, was not to be found in my data set.

I only realized this was a bug when I woke up this morning, expecting to see International Coffee Day on my web extension. I saw no rhyme or reason day and I knew that I had not correctly parsed the data from the Time and Date Website.

## The Front-End

I used the XMLHTTPRequest JavaScript method to retrieve the JSON file I created in my Python script. I retrieve this file at the same time as the "quote of the day" that I discussed yesterday. This means that I only need to retrieve the site once per day. [^1] Once this file is loaded, I locate the entry in the dictionary that maps to the current day of the month and month of the year. Today, that day is 01/10.

It is somewhat wasteful to render a whole file but I did not want to build an API with this data. My goal with this JSON file is to make my new tab browser extension work. I did consider writing a "fun holidays" API but I would then be building something that I myself would not want to maintain. I like to maintain as few programming projects as possible. An API on top of a browser extension (and everything else I've built) is too much.

I only load the whole file once per day so the performance impact is minimal. I store the fun holiday in local storage for later use, like the quote of the day.

## Conclusion

I did say that I had two itches to scratch. The other itch was small. On my birthday, I wanted the site to say "It is your Birthday" instead of "There is 0 day until your birthday". This is the text that appeared on the previous version of my new tab extension. I made a small modification to my code so that, on the day to which I have been counting down, it says 'It is X!', where X is the day. In this case, the day is my birthday and International Coffee Day.

I am happy with the new tab extension. I have published the code on GitHub if you are interested in seeing how it works. To set up my extension, you'll need to install it as a debugging script. I registered it for private use on the Mozilla Developer website. That's only because debugging scripts expire when I close my browser. There is one minor issue with the script that I'll probably fix at some point. Because the page loads so quick, sometimes the quote flashes on the screen instead of loading with the rest of the page. That's a task for another day. In the mean time, I'm going to enjoy my birthday!

*You can view the code for this project on [the project GitHub page](https://github.com/capjamesg/newtab).*

[^1]: If you did not read yesterday's post, I encourage you to do so. It explains why I only retrieve the quote of the day once per day, and how I do it.