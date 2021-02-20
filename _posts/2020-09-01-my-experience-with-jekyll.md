---
layout: post
categories: ["IndieWeb", "Post"]
title: "My Experience With Jekyll"
---

If I do say so myself, I'm becoming somewhat of a Jekyll aficionado. I decided to use Jekyll to build this site on what I would say was a whim. I didn't have a clear idea in mind of what structure I wanted to use. I knew one thing: I wanted the site to be static. My initial idea was to write all the HTML myself but then I realized that would not be practical given how many blog posts I write. 

After using Jekyll for a few months, I've come to love it as a static site generator. It fills all of my needs. The top need I had was to be able to easily manage all of my blog posts. Jekyll does this exceptionally well. I can write posts in markdown and Jekyll generates a feed of those posts. Jekyll also creates an RSS feed of all my posts. I like this because I don't want people to have to come to this site and check for a new post to know if one has been posted. Although you can expect some consistency from my writing, you never know if I'll write fewer or more posts without visiting or using RSS.

## Jekyll and the IndieWeb

I wanted a static site because it is more sustainable than a dynamically-generated site. My last site was built using React.js and Next.js. That's too much tech for a personal website. This website is light and simple. I am unsure how light each web page is but I know that the site loads significantly faster than my last one. This site is only HTML and CSS. There are a few images around the site but not many.

I've found that Jekyll fits in well with the principles of the IndieWeb. Above all, Jekyll makes it easy to set up a personal website. That's step one. Once I had my personal site up and running, I was ready to explore other features on the indie web. Without one, I couldn't do much. It was so easy to get started and that was a big deal for me. I was looking to build a light site and I'm willing to bet that if I had encountered any more friction I probably would have built this site using HTML, only to change later on.

## The Limitations

Jekyll does not meet all of my IndieWeb needs. The biggest need that is not met is that I cannot share webmentions on my blog. Well, I can. That's a lie. It's just not practical to do so. If I were to share webmentions on my blog posts, I would have to change how each post is rendered. I would need to query a webmention API for each post I have written. I could just get a list of all of my webmentions but then I would have to sort them and then render them on their respective pages. It would be a lot of overhead.

I do have webmentions enabled on my guestbook. If you visit this site and want to leave a message, you can do so on the [guestbook page](/guestbook/). The overhead for this page is pretty low because rendering it only involves one API request each time I generate the site. Still, it's one more API request. I do notice that making this API request slightly increases the time it takes to render my site.

Jekyll, like many other static generators, regenerates every page when the site is rebuilt.[^1] For my site, this is not too much of a problem but it does have performance ramifications. When I am building a new version of my site, it takes a while longer than it used to. This is because I have around four plugins that I have built to generate pages on my site. I believe four API calls are made to different web services before the site can be completely generated.

I wish there were a way for Jekyll to only generate pages where a change was needed but I can't think of how that would work. This limitation is the reason why I only display five days of my quantified self data on my fitness page. I did write the code that would save archives from further back but it is impractical to generate all those pages. For each additional page that I wanted to generate, it would add valuable seconds to the build time of the site.

## A Good Tool

Jekyll suits my needs just fine. If I were to be doing more, like building a complex feed using ActivityPub, or syndicating more of my content, then I'm not sure if Jekyll would be as useful. I know that there are quite a few people on the IndieWeb who use it. What I've found is that Jekyll is great for content-driven websites. That's what this site was at the start. Before I added in custom plugins, this site was just a place for me to share my ideas. Now that I have a few plugins enabled, it is clear that Jekyll is not great for every use case.

I'm going to continue using Jekyll. I cannot promise that I will forever because I have changed my site three times this year alone. First, I built the React.js site. Then I built the first version of this site which used a minimal format. Last weekend, I made a few significant changes that added new quantified self data and changed the structure and color scheme of this site. Who knows what tech I'll use in the future. What I like about Jekyll is that it is lean and powerful. It's not too bloated. I do wish that I didn't have to generate every page even when no changes have been made to that page but that's a downfall of using static site generation. I'll live with it.

[^1]: I have not done much research on other generators so please let me know if there are others that support this behavior.