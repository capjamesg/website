---
layout: post
categories: ["IndieWeb", "Post"]
title: "Checking My Webmentions Using RSS"
indieweb: true
indienews: true
---

I have been using the webmention.io dashboard to check my webmentions. This is all I needed in a webmention reader. I'd check my webmentions every now and again because it was uncommon that I would receive one. When I did receive a webmention, I'd add writing a response to my mental to-do list and I would get around to sending one whenever I could. I like the manual process. It's fun to write and send a webmention.

I have been receiving more webmentions. I've found myself checking webmention.io more often. I'd then have to click on each webmention link and then read the response. Because I am now more interested in the webmentions that I receive, checking a dashboard manually every day, opening different links, and keeping a mental note of those to which I should respond is more arduous. I need a replacement. I need a way to check my webmentions more effectively.

I had an itch that needed to be scratched. After some contemplation, I arrived at a potential solution. I thought it would be good to be able to check my webmentions from RSS. I consume a large amount of content over RSS, despite only using an RSS feed reader for about two weeks. My RSS feed is often open. I find it is easy to sift through articles to find the ones that I want to read on RSS. This is a key feature I wanted in a webmention reader. It should be easy for me to access and navigate through my webmentions.

## Converting My Feed to RSS

Webmention.io has a handy API. Their API lets me receive all of the webmentions saved on webmention.io. I presently use this API to generate the data files that render webmentions on this blog. I knew that the webmention.io API would give me the JSON data I needed. I'd be able to access when each webmention was sent, received, and the contents of each webmention.

The issue was that RSS uses XML whereas webmention.io uses JSON. I needed a bridge. That's when I decided to write a Python script to convert my webmention.io feed to an RSS-compatible XML feed. To do this, I used a tool called `python-feedgen`. I'd experimented with this package a few months ago for another project and it appears to be the most comprehensive RSS generator in Python.

The `python-feedgen` package lets me define the metadata for my feed and create individual entries. To make my application work, I needed to combine the data from webmention.io and `python-feedgen`. I wrote a for loop that goes through all of my webmentions and creates individual entries in RSS. This for loop formats the dates for each webmention and creates an appropriate title. The structure for a title is:

```
Webmention by [Author] on [Publication]
```

The description of each RSS entry is the contents of the webmention. I add the source and the target URLs from the webmention.io API so I can see what page a webmention was sent to and the URL for where I can go to see the complete webmention. Building the structure of an RSS entry was largely trial-and-error. I've still not got the source and target URLs to appear on their own lines. This is a small itch that I can fix later down the line.

## Reading Webmentions with RSS

My script must be executed to generate my webmention feed. It is not a server-based application. To make my application work, I needed to make sure that it could collect my webmentions often so that I'd have an up-to-date account of my webmentions in my RSS feed.

I have deployed my Python script on a server. I wrote a cron job that executes the script every five minutes. This means that my RSS feed will only ever be a maximum of five minutes out of date at any time. I can live with this. My webmention XML feed is saved to a web server so that I can retrieve the feed. This process happens independently of the website you are viewing right now because the two projects are independent. One uses Jekyll; the other uses Python.

I use NetNewsWire as my RSS reader. After I had deployed the server script, I added the URL of my new RSS feed to NetNewsWire. After waiting a few seconds in which I was worried that my code may not work, all of my webmentions appeared. I now had a fully-functioning RSS webmention reader. As a test, I tried to send myself a webmention. The webmention showed up on my feed.

Here is how each entry appears in my RSS feed:

![A webmention entry in the NetNewsWire RSS reader client](/assets/webmention_rss.png)

I plan to use my RSS reader as the main place that I consume webmentions. The webmention.io dashboard is helpful for testing and deleting test webmentions but it is by no means a full-fledged reader. I'll now be able to stay more closely connected with my webmentions because I'll get an RSS notification in my feed whenever I receive a webmention.

You can view the script that powers my webmention.io RSS feed tool on [GitHub Gists](https://gist.github.com/capjamesg/0815b752a3785e6c878fda0e64c57d5f).