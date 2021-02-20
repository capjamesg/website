---
layout: post
categories: ["Coding", "Post"]
title: "The Philosophy of Static Websites"
---

I see websites in two categories: dynamic and static. I had a dynamic website earlier this year. Maintaining it took a lot of work. The one factor that made me hesitant to move to a static website was that I had a few features that relied on my site being dynamic. I had a grid which showed the days on which I had and had not written a blog post. I did not make that grid on this site because, at the time, I did not think it was possible.

I chose Jekyll to build this site to cut down on maintenance time. Most of the content that I publish to the internet is written. It is in the form of a blog post. I was happy with using Jekyll because it was built for writers like me. Posts are written in markdown. This works well with the editor I use to write my blog posts, [Typora](https://typora.io/). I can change the templates for my posts easily.

## Complicating the Site

Like any technical project, it's easy to make a website more complex than it needs to be. I am presently asking myself: how complex does this site need to be? What features do I want to offer to the world? I am asking these questions because maintaining this site has become somewhat of a burden over the last few weeks. It's evolved from a place where I share my writing into a side project of its own.

I like tinkering away with this website. There's always something new I can do. I have taken great pleasure in adding [microformats](https://microformats.org/) support to a lot of the content on this site. I am presently thinking about how I can do this with my coffee tracking data. Adding microformats has let me learn about a whole new world of data standardization. Microformats integrates so well with the IndieWeb. Webmentions rely on microformats. I've been able to build knowledge that I would not otherwise have been able to build because I've been working with these technologies in practice.

Microformats is a useful feature on this site. My webmentions are marked up using microformats so that they are compatible with other tools. My article are marked up so I can share them on sites like IndieNews. It has taken a long time to add microformats to this site but that's because I've been doing a lot of reading alongside the implementation process.

There are other features that I am not sure add as much value to the site. I show my quantified self data on this website. I only show five days worth of data. I do not know whether it's worth showing this data because it is quite personal. I added it to the site as both an experiment in using Jekyll plugins and as a means of self-expression. Quantified self has become like an art. I've watched a lot of lectures on the Quantified Self website that show people going really deep into their data. I like doing this. The question is whether it should be part of my site.

## The Intent for This Site

With any software project, I have to ask myself what the intent of the user is. Without knowing this, I have a hard time crafting a pleasurable user experience. Where things get complicated is that personal websites are, indeed, personal. My site is a place for me to come and share my thoughts. I am not sure what it is that I really want to share just yet. I'm still exploring.

The quantified self data made for an interesting discussion at HWC. People analyzed my data. Someone remarked on the consistent cadence on which I fall asleep. I took it as a compliment. I loved seeing that someone had derived value from the data that I posted. Although I do wonder whether this data has any place on a personal website like mine, where content is king.

I am at the stage where I'm looking at all of these interesting technologies and asking: what can I do? It turns out that, in many cases, the technologies with which I experiment have limited use. I gave up on the [sourcehut mirror](https://github.com/jamesgoca/sourcehut-mirror), at least for now. I still have an itch about syndicating my GitHub repositories. It's just not big enough to merit my taking the time to evaluate how to execute on a mirror project for a second time. I do want to display my quantified self data online. I'm just not sure how best to do it.

One idea that has come to mind is creating a second site that hosts everything else. It would be somewhat of a playground. This site would be all about the content. My podcasts and articles would live here. The other site would be home to my coffee data and my quantified self data. The problem with this is that I'd be fragmenting my online presence. I would still have control over everything I host but it would take more time to maintain my infrastructure. I'd probably end up using a dynamic server for my other site. That seems overboard for my use cases.

I am hesitant to remove features from this site because I want my content to be accessible for as long as possible. If you have any thoughts on archiving content, I would love to hear them. I am wondering whether I should archive any page whose link I intentionally break on the [Internet Archive's Wayback Machine](https://web.archive.org/) so that I can always say "this was here at some point, here is the proof." There's nothing groundbreaking in this post just yet. I need time to think.