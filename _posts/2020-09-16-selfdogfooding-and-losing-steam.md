---
layout: post
categories: ["Coding", "Post"]
title: "Self Dogfooding and Losing Steam"
---

There are two types of posts I write about programming. The ones I like writing most are those where I discuss how I built something, or how I intend on building something. It's fun to explain how I build projects. I like the technical details. This is not one of those posts. This is a post about what it's like to be a developer. The developer life, if you will.

I recently decided that I was going to work on a personal bookmarking project. There was a voice at the back of my head from the start telling me not to build the project because I did not really need the tool. I decided to go ahead anyway and build the bookmarking application. I convinced myself why I needed to build this tool.

## Starting a New Project

Pocket is more bloated than I would like. I don't find myself going back to my archive. I feel like this is somewhat of a waste. I bookmark resources for later in case I need to refer back to them. The Pocket user interface sort of discourages mem from going back to look at what I have bookmarked. I would like to share my bookmarks with others. I'm going to write a monthly post with a list of my bookmarks.

Shortly after I decided to start this new project, I begun. I set up a GitHub repository and initialized a Flask instance. There is something quite freeing about starting a new project. I'm working from a blank slate. Every decision about a project I am going to work on is yet to be made. There's so much work ahead to do. I get excited. Still, as I was setting up the project, I had a voice telling me not to continue.

## Building Bmrkme

I called my project [bmrkme](https://github.com/jamesgoca/bmrkme). It's short for bookmark me. [^1] The idea was simple: to create a stripped-down bookmark manager. All I wanted was the ability to save bookmarks. Bookmarks should have two categories: to read and read. I want these two categories because I often find that I bookmark something after I have seen it so that I can come back to it. Having a clear and visual distinction between read and unread bookmarks would be useful to me.

Then I decided that I wanted to build a public feed. This feed would let me share bookmarks with the outside world. This is another feature that Pocket does not have. I wanted to have a place where I could link with a live feed of my bookmarks. I tried to implement this feature on my website but for the reasons I outlined in [yesterday's post](https://jamesg.blog/2020/09/15/privacy-social-media-and-this-website.html) I have moved back to the article-based structure for this blog. A new bookmarking project, I reasoned, would be a good place to build this feature, away from my personal website.

I got to work on building bmrkme. I built the "read" and "unread" feeds. I created a simple profile page. I decided to store all my bookmarks in files because I did not want to set up a database. I wanted my bookmarks to be readable in a plain-text JSON file. This was good all around. It cut down my implementation time and saved me from having to look at the sqlite documentation to build what should be a simple project.

After around an hour or two of work, I had a project I was proud of. My mind started to think of new ideas. I built the profile feed but then I realized that I would need authentication if I were to share the feed. How could I deploy my bookmark manager and have a public feed without having an authentication system to protect the ability to create and edit bookmarks? Too much was going on. I thought about adding microformats support.

## Losing Steam

I lost steam working on the project. I have stopped coding. This is a mistake I have made many times as a programmer. I get so caught up in the technical details of building a project that I forget to consider whether I really need it. I was good at identifying what technologies I did not need. I didn't set up a JavaScript app. Aside from one line of JavaScript for the bookmarklet feature, the project was only HTML, CSS, and Python. I like to use lean technologies.

I work best when I am self-dogfooding. That is the reason why I've been able to make so many changes to my personal website. I built the micropub API because I found an itch that I wanted to scratch. My position on privacy and feeds changed after watching The Social Dilemma but, at the time of developing the project, I was happy with the direction in which I was going. This bookmark project felt a bit more pressured. I told myself that it would look nice on a portfolio. That's not how I like to think about programming.

I can build anything with code if I set my mind to it. With so much choice, I do not have the time to spend on projects that I do not really want to build. I wanted to build bmrkme because I thought I had an itch. Had I stopped for a day and thought about whether I really needed to build the project, I would have probably noticed that I did not need a bookmark manager. For all of Pocket's deficiencies, it works. I'd rather save my energy working on projects where I have a strong itch that I need to scratch. In other words, I correctly engineered the solution to a problem that I was not *really facing.*

With the power to code comes great responsibility. I need to exercise the responsibility to work on what really matters.

[^1]: I understand I did not choose the best name. I struggle to brainstorm names for projects.