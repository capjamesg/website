---
layout: post
categories: ["Web", "Post"]
title: "Rethinking the Blog"
indienews: true
indieweb: true
---

The reason this blog still exists today, after going through so many iterations, is that I always self-dogfood. This is a term in the IndieWeb community that means that I use my own creations. On my blog, everything has been built by me, for me. I haven't thought about whether my code could be used by other people. It probably could. It's all on [GitHub for anyone to use](https://github.com/jamesgoca/blog/). I have licensed my code under an MIT license so anyone can use it.

Over the last two days, I have found myself frustrated by this blog. My primary concern is scalability. When I say it out loud, I do wonder why I am so worried about how my site will scale. With all of the computing power available today, it would take a very long time for me to reach a point where my website rendered slower than a point I deem acceptable.

I am worried about scalability because I want this code to be lean. I don't want to be bogged down by slow rendering times that make changing my site difficult on my local machine. I like speed. It's the very reason that I moved from a site powered by React.js and Next.js to a static website. The way I see it, I have three options: build my own dynamic site, continue to use Jekyll, or look into another dynamic site generator.

## The Dynamic Option

When I had a spare moment yesterday, I noted down what benefits of having a dynamic website are most important to me. The highlight was that I would have more control over the content that I share on my site. I would be able to experiment with new types of content because I'd have access to a database. My database could keep growing to support thousands of entries. I believe that if I had the option, I would be creating content on a similar cadence for this website between my blog posts, reviews, quantified self reports, and other data that I would generate.

Having a database gives me a lot of options. I know how powerful SQL is. I could use it to analyze how I post data over time. I could use it to easily support multiple post types. I could integrate my site with tools like Micropub to share my content on the internet. The question is not whether databases give me options. I am wondering whether they are giving me the right options.

I must note the educational benefit of building a static website. I am unsure what technology stack I would use. Flask seems to be the most appealing. I have quite a bit of experience with Flask and so I could probably get quite far in a short period of time. This is speculation. When I look at what I would need to do to set up a Flask site, I see tons of work that is, when I am really honest with myself, unnecessary.

## The Static Option

I chose a static website for simplicity. My last site made API calls to Airtable to analyze my coffee data. I had a button on my desk which, when pressed, updated a counter on my site which said how many cups of tea I had drank that day (back in the days where I was more of a tea drinker). These were *features*. They were good additions to the website.

I can remember myself getting stressed about the state of my site. React, for a blog? It may work for some people but for me it seemed like too much. What's more is that I got lost in components. I did not really understand how the site worked on a nuts-and-bolts level. I knew that it worked and that was good enough for me.

Static websites introduce new constraints. I cannot create database tables for new types of content. Do I really want to have that option? I'm not sure. I like the current structure of my site. Everything is so visible. All of my posts are stored in markdown which I believe is easier to maintain than a database. A few days ago, I went and updated all of the titles on my blog posts to use the correct capitals. It was bugging me for a while that Jekyll just capitalized the first letter of each word.

I went back and made the requisite changes to all ~60 or so posts. It was manual but it was so easy. With a database, I would have had to write individual queries for each post. That would have been a pain to do. I probably would have given up on the task before I had finished. Maybe that would have encouraged me to find a way to update my posts that I cannot presently envision. Who knows. 

I like having a Jekyll site. I am proud to be on Jekyll. My content is easy for me to understand. I have a folder called `_coffees` where I am going to store my coffee reviews. I have a folder called `_posts` where my posts live. Adding new content to the site is simple. That's what I like and need. The more difficult it is for me to update my site, the less likely I am going to do it.

## Other Generators and Next Steps

I came across [Jamie Tanna's personal website](https://jvt.me/) yesterday. It was not the first time I have been a guest. [^1] I read that his site was powered by Jekyll and I got excited. I thought someone had cracked the issues I was facing with scalability. It turns out that he moved to another generator, Hugo. His Jekyll site took him far but he felt like a change was necessary. Jamie documented the process of moving over to Hugo [on his blog](https://www.jvt.me/posts/2019/01/04/goodbye-jekyll-hello-hugo/).

I tried to set up Hugo yesterday to see how it works. One of the thoughts that came to mind is "why am I doing this?" That is a very good question. Why am I looking for another static site generator? What I have right now works fine. It may not work if I have ten thousand pieces of content on this site. That could happen if I build more elaborate bookmarks feeds, or write a lot of webmentions over the years. But what I have now works. It works. It works. [^2]

As a programmer, I have a tendency to over-complicate my work. I spoke about this in a recent blog post. There are so many ways I can improve this site. When I built support for my coffee reviews, I added support for the `h-review` microformat. I enjoyed doing it. I took my work a step further and I learned a lot in the process. I didn't need to be using Flask to learn what I learned. So, for now, I am going to stick with Jekyll.

I am somewhat tempted to place a bet with a friend that if I move to another generator I'll have to give them $100 or something. I haven't quite made my mind up on that one just yet.

[^1]: I do not want to admit how many times I have surfed the IndieWeb webring. It's more than I can count.
[^2]: I am still somewhat trying to convince myself not to take this further than it needs to go. What I have right now is fine.