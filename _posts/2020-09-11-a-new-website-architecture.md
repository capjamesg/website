---
layout: post
categories: ["Web", "Post"]
title: "A New Website Architecture"
---

For a moment a few days ago, I was tempted to build a server-side application for my website. What stopped me from doing so was my memories from building my personal website with Next.js. My site worked. It looked nice. My site lacked one thing. I didn't really know how it worked. There were too many abstractions away from the code itself. I was often confused about why I had made certain programming decisions.

This website is static because I have complete visibility into my codebase. I understand what works and how it works. I am proud of this. Because I know how everything works, I've been able to take steps like implement microformats into my site without too many hiccups. As I said yesterday, I believe that, whenever possible, data should be stored in files. I don't want to rely on a technology like MySQL or even SQLite for my website.

With that said, having a static site has its limitations. The biggest one for me is that I cannot syndicate content from other services to this site easily.

## Static or Dynamic?

Jekyll has a feature called plugins. I have a folder in my project called `_plugins` which runs three scripts when I build my site. These scripts make my guestbook, music, and fitness pages functional. For instance, the music plugin retrieves my most recent listens from Last.fm and adds them to a page called `music.html` in the static version of my website. This is accessible at `/music/`.

I feel somewhat like I am cheating with this implementation. My site, technically, is still static. I am still loading content from files. But some of that content is being retrieved from external APIs before it can be rendered into a file. These API calls add a few seconds to my build time. I've got to query a few different websites before I can build this one.

That is not the biggest issue. What frustrates me about my current setup is that my content is ephermal. Almost every time I build my site, the data on my fitness and music pages will change. This means that what you see in the morning may be different to what you see in the evening. There is no backup of these pages. The data is pseudo-dynamic. I want to change this.

## A Back-End Microservice

While I was eating a grilled cheese sandwich a few days ago, an idea popped into my mind. What about building a microservice API for my IndieWeb needs? My initial thoughts were that this would be an exciting project to work on. I then started to think that I was overengineering. I didn't want to start a new project that I was going to give up on after realizing it was solving problems that did not affect me (again).

Yesterday I decided that the microservice idea is probably the best step forward for this site. By "microservice," I mean a series of small API endpoints that will power various functions on my site. Each endpoint will power a unique function on the site. One endpoint will create markdown files for my coffee reviews. Another endpoint will mirror my code to sourcehut.

I decided this would be the best step because I want to add features like replies and RSVPs to my site. I have already been experimenting with sending replies to other websites. It has been successful. I like sending webmentions. I also like receiving them (*wink*). The trouble is that writing a webmention and marking it up is somewhat time consuming. I can do better.

My microservice is going to create individual files for each piece of data that I want to display on my site. When I want to create a reply, I will call my microservice. This will take the data I send and turn it into a file. Once this file has been created, it will be added to a local copy of my Git repository and pushed live to my website. The workflow looks like this:

```Write up a reply -> Pass to API -> Process and validate data -> Create file -> Commit file```

Merge conflicts should not be a problem with this workflow because I will only be adding files to a directory in my site.

## The New Feed

To facilitate this change, I am going to modify the structure of this website. At the moment, I store information in collections. Here is a sample of the structure of my Jekyll website at the moment.

```
_posts/
_coffee/
webmentions/
```

Any folder name that starts with an underscore denotes a special meaning. My `_posts` folder is where my posts are stored. `_coffee` is a Jekyll collection with my coffee reviews. The webmentions folder is not a collection because I only store static HTML files in that folder.

I chose this structure because it is clear. When I drink a new coffee, I can add a review to the `_coffee` folder (or, rather, use my Airtable script to add a new review to my site). Creating blog posts is easy. There is a big limitation to this structure. Collections are not treated as feeds. This means that I cannot use pagination on each collection.

The new structure is going to aggregate all of these assets into my `_posts` folder. While the folder structure may be less clear, this new structure will vastly simplify how I treat data. To retrieve blog posts, I can just filter my posts by category. The same rule goes for any other type of content I store.

This change is not necessary. I could use the old structure. I have decided to change because it will give me access to pagination and other features only available to a Jekyll feed. Jekyll only supports one feed per site, as far as I am aware.

## Next Steps

This is a big structural design change. It's not one that I take lightly. I have had visions of how I would implement redirects should I decide to change the structure again. I feel like if I do not try out this structure then I'll always be wondering what it would be like. I see so many IndieWeb websites with replies and likes and bookmarks. I want to have those features implemented on my site. I don't just want them as individual collections. I'd like to have them all as one big feed that I can share with the world.

Deciding on how to implement this new structure has taken weeks. I've wanted to have a feed for data like my bookmarks for a while but I didn't know how to do it. After making the connection between having a single feed and using a back-end service to update my site, everything started to fall into place. I have intentions to add new posts to my site using micropub but I cannot say I know enough about the standard just yet to comment on its utillity or its limitations. First, I'll have to implement micropub.