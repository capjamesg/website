---
layout: post
categories: ["IndieWeb", "Post"]
title: "Social Interactions on the Web"
indienews: true
indieweb: true
---

This morning I was close to giving up on my micropub endpoint. It has taken a significant amount of time to get the project to the stage I am at now. There is still more to do. I have not yet completed the server deployment. I'm having issues with wsgi that I have not yet fixed. I thought that maybe a command line interface would be more appropriate, seeing as how most of the idea behind setting up a micropub endpoint was to make it easier for me to share bookmarks. I then remembered why I am building the micropub endpoint.

One of the core tenets of the IndieWeb community is data ownership. I've never had an experience with a platform making my data completely inaccessible. I suspect it is only a matter of time. It's so difficult to maintain a website. I went into my site restructure with the idea that I wanted to own more of my data. The data that mattered most to me was my blog posts, coffee reviews, replies, and bookmarks.

## A More Social Web

I have wondered whether moving to a feed-based structure takes out some of the fun behind my website. My site is closer, architecturally, to many other IndieWeb sites. If you scroll through the IndieWeb webring, you'll see a number of sites that share bookmarks, likes, and replies. I do not feel bad about including these data types on my site. It turns out that these are just some of the most important pieces of data for me to own.

Moving to a micropub client helps me be a bit more social on the web. One of the goals with my `bookmarks` page was to let people see what I was reading. Any IndieWeb article I'd read and liked in the last few days would show up in the feed, alongside every other type of article that I'd liked. The problem was that I was only showing the most recent bookmarks because I was not willing to generate an entire new feed just for my bookmarks. This would drastically increase the time it takes my website to build.

I have built my micropub client so I can take ownership over my data. The benefits of owning my bookmarks were made clear when I tried to import a few recent bookmarks from the Pocket API to my website. I had significant trouble using their API. It must have taken almost an hour for me to get an authentication key and parse the response from the data they sent over.

What's more is that their API did not even have all the data I wanted. I could not, as far as I could tell, access the date and time on which I bookmarked a site. I had hoped to move all my old bookmarks to my site but this is not possible without having access to those timestamps. Depending on an external service for my bookmarks means that I have to bow to their will when it comes to accessing my data.

## Bookmarks, Replies, and Likes

Once I have successfully deployed my micropub endpoint, I will have ownership over my bookmarks, replies, and likes.

Replies are particularly important because they let me interact with other websites. I've received a number of webmentions from IndieWeb community members over the last few weeks and it has been exciting to see people react to my content. I don't even need to build a comments box. All you need to do is know how to send a webmention and create one and I'll see what you have to say about my content.

I am writing more replies to the content I read. I am tempted to do this even for sites that do not support webmentions. This is not too much of a problem at the moment because most of the content I've consumed has been related to the IndieWeb lately. These replies are sometimes a short comment and sometimes they are a longer description of my thoughts on an article I've read. I want these to be easily accessible on my site so that anyone who visits can see them, not just the people to whom I have sent my articles.

When I think about it, likes and bookmarks are somewhat difficult to distinguish for my purpose. A bookmark inherently implies that I liked a post because I usually only bookmark posts on Pocket that I like and want to save for later. I use Firefox bookmarks to track the articles that I have not yet read and want to come back to later. There is a distinction. A like is clearer. It's my way of saying that I did like your content. Not everybody will know my policy on bookmarks, so having a like feature is useful.

## One Feed

All of these posts appear on one feed which is available at `/feed/`. Bookmarks and likes link directly to a resource whereas webmentions and posts link to a page on my site with details on those resources. I have not generated category-specific feeds because this would take too long. I do have my suspicions about the scalability of Jekyll. For now, my setup works fine. I am not going to change to a new blogging engine. I know that I was thinking about it a few days ago but I've really come to fall in love with the Jekyll architecture.

I am using the Quill client to send data to my site. I have not tried out any other micropub clients but I could if I wanted to. They all support the same standard. Quill's onboarding process was seamless. I do wish they had a feature to refresh your site without having to go through the entire authentication flow again. Maybe I'll open up a GitHub issue on this topic. Quill is open source. I am looking forward to being able to send bookmarks to my site using the Quill bookmarklet. It will make sharing data so much easier. Micropub will let me be a bit more social on the IndieWeb. It is impractical to write individual markdown posts for each like and webmention. That's why I have spent so much time building my API.