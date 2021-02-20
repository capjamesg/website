---
layout: post
categories: ["IndieWeb", "Post"]
title: "Micropub and Publishing Content"
---

I have seen articles and posts and messages about [micropub](https://indieweb.org/micropub) a number of times. It's hard to avoid at least seeing the term "micropub" somewhere in the IndieWeb community. I am still not fully sure how it works. What I do know is that micropub just right for what I want to do with my personal website. One of the biggest problems I have with my website is that it is somewhat laborious to post a new article. I have to create a markdown file with the contents of the article. I have to write front matter for every post.

I did not mind this to start. I like the visibility I have into my publishing workflow. I know that every blog post will be posted because I add them directly to my codebase and commit them to GitHub. I prefer to keep my data in files. I hope that this will help preserve the longevity of my blog, even if there comes a time when I stop maintaining my site. I'll always have an archive in Git.

As I explore new forms of publishing content, my site needs to evolve. That's why I have been building a back-end API.

## The Micropub Server

Building a micropub server is no easy task. I have spent days working on my server in my free time and I have still not successfully deployed the final version. There are a few issues with wsgi that are holding up deployment. I hope to resolve these issues soon. What made me commit to the task of setting up a micropub server is that I'd be able to post content to my blog from a graphical client.

When I read more into micropub, I realized that it supported more than just blog posts. The protocol could be used to submit bookmarks to my site and other pieces of data. I'd be able to own more of my data. I have not presently added support for bookmarks or likes into this website because it would be  time-consuming to create a new markdown file every time I wanted to react to someone's content.

The goal with my micropub server is to let me post content without having to go into the codebase. I have chosen to use Quill in the interim as the interface through which I will publish content. Its user interface is intuitive. I liked the setup instructions. Without those instructions, I may have given up on the idea of hosting a micropub server entirely. I'm still new to all of this.

## The New Workflow

The way my server works is like this:

1. I create a post on Quill.
2. A POST API call is sent to my server. [^1]
3. My server reads a markdown template using jinja2 and fills in the content from the API request.
4. The complete file is saved into a version of my blog's Git repository.
5. The updated Git repository is pushed to GitHub.

This is all done in Python. This abstracts away the need for me to go into my Git repository on my local machine and submit bookmarks manually. Handily, Quill comes with a few bookmarklets that will reduce the time it takes for me to react to content.

I was hesitant to start a back-end service for my website. I am happy with this workflow because it is not a traditional content management API. I only use micropub for content management. I am not committing to lots of forms and input validation and authentication and everything else that comes with running an API. It's just micropub and a few custom services for other purposes.

One of these services is my sourcehut mirror project. I have moved the sourcehut mirror from its own repository into a module in my server. This means I can have my webhook server running all the time so that I can create a copy of all the code I post to GitHub. I'm happy this project has come in use. I have been thinking about how to use the sourcehut mirror project. Now I have a server up and running, I have an excuse to deploy the project.

## The Feed

With this new server deployed, I'm moving to a feed-based structure. This means that my site will not just be blog posts. I'll be sharing content like bookmarks and replies. I already did this to some extent but the structure was technically complex. I had a folder for webmentions and I scraped my bookmarks from the Pocket API. Having a folder for webmentions and not a feed meant that you couldn't view them without navigating to each one individually. Retrieving bookmarks from the Pocket API limited how many I could show on my website.

I plan to post a weekly quantified self update on my site. This will be stored in a file so I'll always have a record of the data. This is another part of the API that I have been building. It's going to be powered by a cron script but it will still rely on the core API I have developed. Having a server to host all of these projects is wonderful. I can set up these sites and forget about them, unless I ever want to make improvements or changes.

I know there is a lot going on. I took the morning off working on my site to spend time with family. I went to my local coffee roastery. I have been thinking about so many ways to change my website. It has been fun. I have enjoyed every moment. Planning out these new workflows lets me exercise my engineering muscle. With every improvement, I'm able to practice a skill. I like reading the [IndieWeb wiki](https://indieweb.org) and then implementing a feature. This is how I've learned about microformats. I've read about a format that suits my needs and then I have implemented it.

[^1]: I decided to call my server "micro." This is because I am hosting a microservice on an API. I have decided to change the name to "Lou." I don't know why this name came to mind, but it did. It came to mind as I was preparing my breakfast this morning. I like the name. Now, I have to update all my nginx configurations.