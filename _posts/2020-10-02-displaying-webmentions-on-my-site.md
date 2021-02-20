---
layout: post
categories: ["IndieWeb", "Post"]
title: "Displaying Webmentions on My Site"
indieweb: true
indienews: true
---

Sometimes I feel like I have to be working on a coding project otherwise I am somehow behind. I do not like to feel that way. I like to code because I can build something meaningful, but what I build is only meaningful if I have a good idea. I'm slowly training myself to step back and to stop worrying about not having a particular project to work on. Making small changes to my existing work is more meaningful than starting something new.

I implemented webmentions about a week ago on my website. I wanted to display all of the comments that I'd received. I presently check my webmentions by navigating to the webmention.io service and reading through the webmentions on my dashboard. I figure there is a better way. Perhaps I could subscribe to them using an RSS feed that I create. Oh! there's an idea that I can work with. Back to the post.

The problem with checking my webmentions like this is that nobody else gets to see them. I wanted to make my webmentions public. When you go onto a blog post, you'll see that there are now a list of webmentions on each post. I achieved my goal of adding webmentions.

## How to Show Webmentions

Most of the features on this site have improved incrementally. If you've looked at any of my posts with a webmention lately, you may have seen that I didn't build the most interesting or robust webmentions section. Every webmention was simple. A webmention would say "Reply by X (Posted on Y)", followed by the contents of a webmention, where X was the name of the person who sent the webmention and where Y was the date the webmention was written.

I feel like this is too basic. I was missing out on displaying important context. Over the last two days, I've tinkered around with my webmentions so that they are more meaningful when you read them.

The biggest change was to use the `wm-property` data point that is provided by the webmention.io API. I use this data point to understand the context of the post that has been sent. Some webmentions are replies, others are likes. I believe webmention.io supports about five or six different contexts. I decided to implement all of the ones that are related to posts.

When someone bookmarks my site, my comments section will show: "Bookmarked by X (Posted on Y)". If you write a detailed reply to a blog post, you'll see that your reply is featured inline on my website. I have considered paginating the responses but I am unsure whether this is beneficial. I could limit responses to around 200 words and then link back to the original post. That may be a good way to cut down on post sizes. [^1]

The contents of each reply are styled with some padding to the left of the element. This lets me distinguish the text of a webmention from the information about the webmention ("Bookmarked by..."). I considered italicizing the comment body but I thought that this would make my site less accessible. Screen readers should not read the replies to a post in their special italics context because replies are, in my eyes, an essential part of the web page.

## Designing Around the Webmention Section

I made a few changes to the end of each article. I now display a section called "About this article". I added this section to distinguish my webmentions from the additional information I display about a page. Since I added this heading, I've made a few changes to the data. I now no longer italicize the permalink. The permalink for a post does not need to be displayed in italics because it is now part of its own section with its own context.

I display categories, syndication links, and the permalink on three different lines. This makes the content easier to read than showing the permalink and syndication on one line and the categories on another.

## An Engineering Challenge

I ran into a big engineering challenge while I was building my webmention setup. Someone sent me a webmention one day that broke my site. I tried to render my Jekyll site and I couldn't. Jekyll gave me a Unicode error. Evidently, I did not verify the format of the data sent by webmention.io. After doing some digging, I realized that the body of a post could contain Unicode characters, like an emoji. I didn't think about this when I designed my setup.

For some reason that I do not fully understand, Jekyll did not like the encoding of the data I had. When I first encountered the issue, I gave up on trying to fix it. I kept coming back to it in my spare time because I knew that if I didn't fix this issue I would not be able to update the webmentions on my site. I came up with a solution.

For every webmention I receive, I encode the webmention in ASCII, strip any incompatible data, and then decode the data so I can store it as a string. I use the following line of code to parse the body of each webmention:

```
w["content"] = w["content"].encode('ascii', errors='ignore').strip().decode('ascii')
```

`w["content"]` refers to the content of an individual webmention on my website. 

## Showing Images for Webmentions

Unlike many sites on the IndieWeb, I do not display the images of the people who have sent me webmentions. I do show avatars on my guestbook although now I think about it I should maybe change this policy. I decided against showing images alongside each webmention to keep the size of each page as small as possible. If ten people submit a webmention to a page, my website would have to render ten images every time you loaded a post.

I have been unable to convince myself that avatars are important for my website. [Peter Molnar's website](https://petermolnar.net/article/running-a-static-indieweb-site/index.html) does not display avatars alongside webmentions. I like the simplicity of this approach. Having avatars also means that I risk displaying broken images if any of the linked avatars are subject to link rot [^2]. That's not a situation that I want to be in.

I am now happy that my webmention implementation works. I can display webmentions successfully. Each webmention has its own relevant reply context. I don't display images. My setup looks like it fits in with my website. I did feel like my posts were getting a bit cluttered after adding the "About this article" section. I got over this when I added the padding to the contents of each webmention. This change helped me break up the wall of text that was appearing as a result of displaying webmentions. If you have thoughts about my setup, send me a webmention. It will appear on the next build of this site.

[^1]: Here, you can see a live version of me overengineering. I've never encountered a problem with post sizes before. At least I know that paginating responses is an option if I ever need to.

[^2]: Peter Molnar has informed me that webmention.io has a feature that saves avatars to prevent link rot. This does not change my position on displaying avatars. I am still concerned about the performance ramifications of supporting avatars on my site.