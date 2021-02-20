---
layout: post
categories: ["Web", "Post"]
title: "Sustainable Web Design"
---

I have designed this website with sustainability in mind. Earlier today, I read a [blog post by someone who has similarly designed their site from a sustainabillity perspective](https://jamesvandyne.com/2020/08/21/designing-sustainable-digital-products.html). It is nice to see more people who are taking pride in making their websites more sustainable.

As someone who is becoming more conscious of environmental issues, building a sustainable website has become incredibly important to me. I understand that the environmental impact of the internet is hard to quantify. It's even harder to determine the impact of an individual website. Some calculator tools try this to varying degrees of success. I have decided not to get too involved in the weeds. I'm instead going to let my principles of minimalism guide how I build this site and strive to create the best, and most environmentally conscious, user experience.

## Moving My Web Server

I learned today that DigitalOcean powers some of their data centers using renewable energy sources. According to a community post on the DigitalOcean forum, the company reportedly uses 100% sustainable energy sources to fuel their London data center. After reading this, I was inclined to consider whether I should move my web server to the London region from the NYC region at which it was previously hosted.

I have looked into "sustainable web hosts" but I have not found one that I like. The main problem I have encountered is that all of the hosts I've looked at focus mainly on their own site or WordPress hosting. Hosting a VPS, which is what I need for this site and various other projects, is a more expensive service. While I do care about sustainability, I found it hard to justify paying the amount that was being asked just to host a simple server in the cloud.

I decided to stick with DigitalOcean. Knowing now that some of their data centers are powered by renewable energy, I was happy to make the requisite changes to move my server to a place where servers are fuelled sustainably.

You may have noticed that the site was down earlier today. The site may be down periodically over the next day or so, too. This is for two reasons. First, to transition to a new region, I had to turn off my server. This caused the outage earlier today. Continued outages will be a result of the DNS propagation that is going on. These should not affect most people but in case they do that's probably the reason why this site has been, or will be, inaccessible. I feel a need to say this on my blog because I talk so much about accessibility and being able to actually visit a site is the most important part of accessibility.

## Keeping Things Simple

I've been revamping a lot of my blog over the last few days. These changes have been inspired by my recent journey back into the IndieWeb ecosystem. I have felt tempted to add features like Webmentions into my site to embrace the IndieWeb.

I have had to say no to a lot of the ideas that I have had because they will clutter up this site too much. Webmentions are a case in point. I do like the idea of webmentions but the Jekyll extension I found adds JavaScript to a site. What's more, the extension adds a significant amount of time onto my site build time. I have no doubt that the extension is useful but it is not for me right now. I am not up for building my own extension just yet so I am not going to be supporting Webmentions at the moment.

I have also been updating the heirarchy of this site. All of the links that were on my "links" page are now on every page in the footer. I hesitated when making this change because it means that each page is slightly larger. I decided for this change because I believe that the environmental cost of loading a few extra bytes per page is marginal when you consider that to view my "links" page you would have to render a whole new page. I also believe that this change adds to the usability of the site.

That's the thing about sustainability. My goal is not to create a completely sustainable website. To do that, I'd power my server using solar and I would probably only render plain text. This sounds like a good plan but it's not what I want to do with this site. My goal is to create a sustainable website that fully meets my needs. My needs include showing a few images here and there to supplement my content. I want to add some personality into my site. That's why some trade-offs are required.

I do not let these trade-offs get in the way of experience. Right now, you'll notice that there are two Airtables embedded into the "coffees" page on the site. I am going to remove these and replace them with a statically-generated alternative. Airtable adds too much bloat to my site. I added the sheets because they offer valuable content: a record of my coffee brews and the blends I am drinking. I am not happy with Airtable's embed solution so I will build my own that is more effective. I guess the IndieWeb is really rubbing off on me.

## It's an Ongoing Process

Building a sustainable website, as the blog post to which I linked earlier reminded me, is not a one-time event. Every time I make a change to this site I like to consider how I can make the website more sustainable. Does the change I want to make improve the usability of my site? Does it do so in a sustainable way? Are there other ways I can implement that change that are more sustainable?

I sometimes notice opportunities for changes to be made. When I designed my "life stack" page, I realized that the screenshot of my phone, after minification, was over one megabyte. That's way too much to ask you to load when you come to this site. I'll hazard a guess that Airtable takes about as long. Airtable is actually affecting the usability of this site in several ways: it is not accessible from a screenreader perspective, to my understanding, and it takes so long to load that a white box appears in the place of an embed for a few seconds as soon as you start to load the page.

I removed the image of my homescreen and replaced it with a plain-text list. A simple change but one that will make the site significantly faster to load.

I'll keep making changes as I find new ways to make this site more sustainable.