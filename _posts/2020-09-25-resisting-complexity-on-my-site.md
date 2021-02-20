---
layout: post
categories: ["IndieWeb", "Post"]
title: "Resisting Complexity on My Site"
indieweb: true
indienews: true
---

I am tempted by all of the IndieWeb websites to add more features to this site. Yesterday evening, I had somewhat of a realization: the parts of my website that stand the test of time are those that are simple and do not require any overhead.

I define overhead as being a feature that takes extra time to maintain, or a feature that occupies my mental headspace more than it should. The second definition is particularly important for me. As I learn more about the web, adding new features becomes easier. It becomes more difficult to know when a feature is worth it and when a feature is just me playing around.

## Dark Mode

Yesterday, I wrote a to-do list of ways that I could improve my website. I was busy and so I did not get around to implementing any of the features. I'm happy beacuse after waking up and seeing my to-do list of feature changes, I feel like a lot of them are unnecessary. Dark mode was high on the list.

I know the technical details on how I would implement dark mode. I would create a cookie in JavaScript that stores whether you have toggled dark mode on this website. That cookie would be read on every page load by a simple JavaScript script. If you had toggled dark mode, a few changes would be made to the stylesheet. I would probably make the background close to black and choose a contrasting text color.

The idea behind dark mode is that it would make my site easier to read for some people. While I do write in a light editor, I do most of my tasks in an editor with dark mode. From the day I set up Sublime Text, I have used dark mode. I know how much people love dark mode. When I think about it, this feature is not so much about technical aptitude. It is a case of trying to build for everyone.

## Webmentions

I thought about how I could add webmentions onto this website. I got excited about webmentions after someone in the IndieWeb community told me about a way to notify people when I mention them in my blog posts. After evaluating the existing options, I was unimpressed. This is something that I have experienced a lot on the IndieWeb. There are so many great tools out there but most of them do not fit into my workflow. I like to build for myself.

To implement webmentions, I thought about writing a plugin that retrieves all of the webmentions that have been sent to my site. There is an API endpoint at webmention.io, the webmention provider I use, that would let me retrieve these webmentions. I would write a custom front matter tag that would add these webmentions into my site. I know that [Aaron Gustafson has built a Jekyll webmentions plugin](https://github.com/aarongustafson/jekyll-webmention_io). I did not want to use it because I have very limited needs and I like to keep the overhead low on this website.

I am not adding webmentions for the moment. I keep coming back to this idea. My old excuse for not adding webmentions was that, at scale, they would not perform well. That's another instance of the ["at some point" antipattern](https://indieweb.org/antipatterns) that is so common in tech. My new *reason* for not adding webmentions is that they would make my site just a little bit more complicated. I'd rather keep this site simple.

## The Weather Station

My weather station shut down after a week in operation. To all those who saw the "New! Weather Station" banner on the site and who were unable to see it, I apologize. My weather station is out of commission. One reason is because I bought a heat sink for my Pi and it turns out that heat sink imposes on the GPIO pins. I now have a heat sink stuck to my Pi that I cannot remove and that obstructs the GPIO pins. It's not an ideal situation.

I shut down the weather station because it was too much to maintain. I didn't want to keep my weather station on at night beacuse I like to have all of the technology that I use turned off before I sleep. Although the chances of my Pi causing a fire are minimal, they are higher if the Pi is on and I am not able to respond if I notice anything going on.

## The Philosophy of Simple Sites

People who have been visiting this site for a while will know that I have gone through a lot of ideas. I built a micropub client. I displayed quantified self data. I created a directory of all the coffees I have consumed. It became too much for me to manage. This website is only part of my day. I don't have time to check that all of coffees are in the directory and that every detail is up to date. This is the same reason why I do not have an About page. I change so much that my about page would become yet another thing for me to change whenever I do.

I am actively changing this site to meet my needs. Yesterday, I added in a new feature. I changed the weather station banner and replaced it with a banner that changes every time I build this site. I may talk about the technical details in another post. I have just decided that I am going to make the banner change on build time. That's easier than making it change every day. I built this banner because I wanted to show interesting messages to my visitors when I do not have an announcement to make.

This post is somewhat of a continuation on my last post. When my personal website is such an important project to me, it is easy to add new features. I'm not sure I will ever be able to resist tinkering around. I don't want to completely opt out of changing this site. It's a bit of a pain for visitors but this is a site for me. If you come here, you may get a pleasant surprise if there is a new feature available.

I like to build for this site because I can learn a lot by coding projects that are for me. There is a fine line between a feature being cool and becoming a burden. I don't want this site to be a burden. It should be a playground for my ideas.