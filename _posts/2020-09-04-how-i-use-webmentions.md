---
layout: post
categories: ["IndieWeb", "Post"]
title: "How I Use Webmentions"
---

I sent my first webmention yesterday. Well, that's not completely true. I have sent one or two in the past but they were just test-runs. Yesterday was the real deal. I had some thoughts on a blog post I read and I decided that I'd share them with a webmention.

I like the idea of webmentions because they let me take complete ownership over my data. I do not need to put my faith into a comments system. There is no way that my comments can be edited other than by me. If I want to delete a webmention, I can, at any time, for any reason. While some of these features may be offered by websites, there's never any guarantee that they will always offer the ability to modify the data I submit.

## Receiving Webmentions

I noticed a few people have mentioned my website on their sites. That's what a webmention is: a mention of a web resource. It took me a while to understand that a webmention is not just a way of posting comments. I believe that you can use webmentions as bookmarks, or as replies, or likes. I haven't looked into these implementations yet. They are outside the scope of what I have done on this blog.

On webmention.io, I can see a feed of the people who have mentioned my site. The first entry to pop up was a bookmark of a post I wrote a few days ago on the IndieWeb and quantified self. It was nice to see that someone had mentioned my site. Someone read my post. As I was saying to a fellow IndieWebber in the chat, when I think about it, I often feel like I'm just throwing words into the cosmos. Webmentions make blogging... social.

My site displays webmentions in one place: on my guestbook. I have been fascinated with the idea of guestbooks since I learned about them. If you come to this site and you want to share something before you leave, you can do so, in a shared forum. You can see who else has visited my site. I do not think that you need to sign it before you leave. It's just a feature that is on my site if you want to use it. I'll be grateful to anyone who sends one.

I do not support webmentions on any other page because it would add too much time to the build of this site. It already takes eight seconds for my site to build. Adding webmentions would mean that I'd have to retrieve all the webmentions for my site and add them in to their respective posts. If my blog became more popular, this would present an issue. I don't want to implement a feature that I would probably have to remove later.

## Sending Webmentions

I sent my webmention yesterday using a tool called Telegraph. Telegraph is part of the p3k stack. I haven't looked into other parts of the stack but from what I understand they are all tools that are built for the IndieWeb. Telegraph makes it really easy to send a webmention. I did try to send one through Webmention.io's interface but I found that I was sending the webmention to the wrong site because I used the wrong link.

Telegraph is great because it lets me see the status of my webmention. I know I can check this on webmention.io but it is somewhat inconvenient. Telegraph has a very visual UI which is useful given the technical nature of webmentions.

I created a new folder on my blog called `webmentions` for me to store my webmentions. I have decided to name them using numbers: `1.html`, `2.html`, etc. As far as I am aware, there is no naming convention that I need to use. My webmentions are presently just HTML files. This is because my goal yesterday was not to set up a complete webmention stack but just to send one. I used [Aaron Parecki's webmention tutorial](https://aaronparecki.com/2018/06/30/11/your-first-webmention) to help me write the webmention that I sent. [^1] Now I know the structure, I feel much more confident about sending webmentions.

My next step is to create a simple Jekyll `includes` template for my webmentions. This is more for code cleanliness than anything else. It will not affect the function of my webmentions. At some point, I'll have to do a full audit of the cleanliness of this site. That's a job for another day.

## Continuing to Use Webmentions

Sending a webmention is definitely not as easy as sending a message. I intend to send webmentions to sites where I want to share my thoughts about a post publicly. Right now, I don't see webmentions as a way to start a conversation. I'll probably try to email anyone whose blog post leaves me with questions, or I may send them a message in the IndieWeb chat if they are on there. I do see webmentions as a good way to give feedback, or to add a thought or two to a post.

[^1]: I cannot recommend this tutorial enough if you are new to webmentions.

