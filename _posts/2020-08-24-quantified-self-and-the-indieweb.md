---
layout: post
categories: ["Quantified Self", "Post"]
title: "Quantified Self and the IndieWeb"
---

I'm back on the quantified self train. I have tried quantified self a number of times in the past but it has never stuck. More recently, I've become interested in quantified self because it gives me a lot of data with which I can experiment. While each individual metric may not be useful on its own, over time I will be able to collect a lot of data about myself.

I am unsure whether I'll keep at quantified self but this time, for some reason, I am more hopeful. I've started to play around with quantified self metrics on this site and it has brought me a lot of joy. Even if the statistics just sit on this site, at least I'll know that it was fun playing around with them.

## Deciding on the Parameters

When I began with quantified self, I had a big question to ask: what am I going to track? This was partially decided for me by the limitations of Exist.io, a tool that aggregates quantified self data. Their platform only supports a certain number of integrations. I have mostly stuck to using services that integrate with Exist.io so I can benefit from using their platform.

I am using services like Fitbit to track my exercise and Dark Sky to track the weather each day. These services are all great places for me to start because they do not ask me to do anything. I've configured these services and they will gather data in the background. No manual data entry is necessary.

There are a few exceptions. I have been tracking the coffees that I drink for the last few weeks in Airtable. This is a manual process but I'm fine with it because I spend a lot of time writing notes about my coffees. My coffee tracker is an important part of my journey to learning more about coffee. I have also created an Airtable to track the television I watch. I have only watched one documentary this year and so I think it will be a pretty low maintenance project.

## Building the Infrastructure

While Exist is a great platform to view my data, it has one big limitation: my data is not public. This is fine because there's a lot of data I do not want other people to see. That's why I have decided to build my own IndieWeb quantified self infrastructure.

I started by creating a simple Python script that scrapes data from my coffees Airtable. The script uses jinja2, a templating engine, to render my coffee spreadsheet as a HTML document. There were a few styles to make the page prettier.

I used a similar approach for my quantified self data. This took a bit more time and is still very much a work in progress. There's a lot of data to go through and every value has its own units and needs to be represented in its own way.

The drawback with my jinja2 scripts is that they were separate sites. Over the weekend, I had created two subdomains, "coffee" and "qs" (which stands for Quantified Self) to accomodate these new sites. This is complex for both me and viewers of my site. Why should people need to go to another site to see this data? That question is what prompted me to start building a Jekyll extension.

## Quantified Self on My Website

I have started to move my data over to this website. My initial hesitation was that I'm not as familiar with Ruby as I am with Python and I need to do a lot of exploration to figure out how best to present data. While I have encountered a few roadblocks, so far the migration has been going well.

I much prefer the idea of having my data appear on this site. For one thing, I do not have to maintain separate repositories to show my coffee and quantified self data. Second, because the data is on this site, I do not have to send people to other websites when I link to this data.

I am still at the data exploration stage. The quantified self page is live but it has a few problems. The units do not appear correctly in some cases. The coffee page is pretty much done for now. I'll maybe make a few changes if I end up changing how I track data.

## The Static Approach

The reason that I've chosen a static approach is that I don't want to query Exist and Airtable every time I want to show this data on my website.

As I said in yesterday's blog post, embedding an Airtable into my site adds a lot of unnecessary overhead. Embedding an Airtable also comes with a number of accessibility concerns which are not easy to rectify. A static representation of my Airtable data loads much faster and has accessibility out-of-the-box. This is because I've used semantic HTML elements like `<table>` to build the list of my coffees.

The quantified self data that I show on this site does not need to be updated every second. I don't sync up my Fitbit every hour of the day anyway and so the data would always be behind. I do know one thing: my data should not be out of date by any more than a day. That means that updating my site on a daily basis should suffice. This approach lets me save bandwidth and time spent generating the site.

Where the IndieWeb fits into all of this is that I am taking control of my data. I am creating a copy of my data that is displayed on my site. I've noticed that a few people in the IndieWeb community are interested in quantified self and so I hope that some of the learnings I'm sharing about this process will help others.