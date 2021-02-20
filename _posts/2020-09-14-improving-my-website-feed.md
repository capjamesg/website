---
layout: post
categories: ["IndieWeb", "Post"]
title: "Improving My Website Feed"
indieweb: true
indienews: true
---

Building a feed for this website has been the longest project I've undertaken as part of my site. Most features take a day, or even just a few minutes, to complete. I went into building my site with the mindset that I wanted my site to be simple, both aesthetically and structurally.

What I have come to learn is that building simple software takes time. The software I have been writing these last few days is not as I would like it to be. I am not sure why but my micropub client feels somewhat bloated. I am sure there is a better way that I could structure my code. For now, I am happy with the fact that it just (almost) works.

## The Feed is Live

The goal was to move from a collection-based structure to a feed-based structure. I am presently using a collection for my projects but that is it. I may even move away from this collection when I think about it. The problem with collections is that they do not integrate with tools like Jekyll paginator. I'd have to build my own custom paginator and generate category pages and this would take time to build.

The new structure, from my perspective, is much easier to understand. Every post is in the `_posts` directory. I presently support blog posts, bookmarks, likes, replies (webmentions), and RSVPs. I have no plans to extend the number of post types I share at the moment. I'm content with what I have. These post types are the ones that are the most important to me. They let me participate in the social IndieWeb.

Each post type has its own template. This lets me render my blog posts differently from my bookmarks. My bookmark template looks like this:

```
<h1>Bookmark of {{ page.title }}</h1>

<p><time datetime='{{ page.date | date: "%Y-%m-%d %H:%M:%S" }}'>{{ page.date | date_to_long_string }}</time></p>

{{ page.excerpt }}

<a href="{{ page.location }}" target="_blank">View this link (opens in a new tab)</a>
```

My post template contains more tags and is marked up using h-post. Using different templates for different post types lets me make the most of microformats. Posts carry the right microformats depending on their type.

All of these posts appear on the feed on this site. The feed starts on my homepage and continues at `/feed/`. There is a paginator at the bottom of the page to guide visitors through each page. I am content with this setup because I don't need all of my posts to be categorized by category pages. That would only add to the build time of my site. Most people are either searching for my recent content or my blog posts. To access my blog posts, you can go to my `/blog/` page. My most recent content is at the start of my feed.

## Automatic Webmentions

I received an email earlier today from someone who said that they had seen the webmention I sent but they had not received it. Confused, I decided to research this issue further. It turns out I posted the webmention to my site and it showed up live on my feed. I forgot to send the webmention. It was only by happenstance that they came across the post when they were navigating my site.

To prevent this from happening again, I have built an automatic webmention syndication feature into my micropub API. I now realize there may be conflicts with this feature and an engineering issue I am still facing. [^1]This feature takes advantage of the [Telegraph API](https://telegraph.p3k.io) to send webmentions. Whenever I create a new like, bookmark, or reply, it will be sent to the creator of the content to which my post is linked. I'll never have to remember to send webmentions again.

I hope this feature will let me be a more active contributor to the social IndieWeb. I checked my webmentions this morning because of the issue I just spoke about and it was so nice to see people liking or replying my posts. Because I do not track my site logs, I have no idea how many people come to this site. I do know that there are at least a few people who spend their time reading my blog posts because some people are taking the time to interact with my content. The web does sometimes feel lonely. Webmentions help me stay connected with the people who read my work. 

## Limitations

This project is not over by a long stretch. The feed is active but there are still a number of problems with my micropub server. The biggest one is that I cannot get automatic deployment with Git to work. I am presently using os.system() to push the files that I create to the GitHub repository where I host my blog but this does not seem to work well with gunicorn, the tool I am using to run my micropub server.

I would like to simplify my code so that it is easier to read. I had thought about trying to make my code reusable for other people but I have arrived at the conclusion that my code is hard to extend. I'm building a custom solution. I now understand why people build their own blog generators. I was tempted to do it until I realized how much mostly unnecessary work I would be doing. But for others, a blog generator is the only way to go. For me, having this custom micropub server is the only way to go.

I do have other "feature" plans for the future. I'd like to post automatic quantified self updates. The code for this has mostly been written. It's just a matter of deployment. I am considering whether I should find something else to work on to take a break. This site has a feed. It works for the user. I've just got to do a little bit of manual work on my end. This is a significant improvement from where I was a week ago.

[^1]: This is one of the many reasons that I write. I figure out solutions to problems and conflicts as I go. 