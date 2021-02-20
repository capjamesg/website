---
layout: post
categories: ["Web", "Post"]
title: "Accessibility"
---

It's a Saturday and I have an announcement to make: I am launching a new version of my personal website.

Over the coming days, I expect to talk at length about the reasons behind this change. This will be the second major change to my website this year. I've made perhaps hundreds of small changes to my site. It has certainly kept me occupied.

A big factor in this change was accessibility. I've been reading about the World Wide Web for the last few weeks and it's become clear just how important accessibility is to the web. I'd be curious to see what the web would be like if it was just hypertext. That curiosity has me tinkering around with using w3m, a fully text-based browser that cannot render images or JavaScript.

I know why a lot of sites I've been going to lately say "Created on a 1820x1080 monitor" or "Best viewed on..." This is largely a relic from the '90s and early '00s internet but it should be brought back. This is an important piece of information that users should know about. If a website was created on a large monitor, there's a greater chance that the site will not be accessible to other devices. I have done my best to plan for mobile versions in the past but I've  found that I build sites that work well on my technology.

I am running an Apple Macbook Air from 2015 with a 13" screen. I use Firefox to access the browser. I use my computer from an external monitor which I believe is around 24". This is a very specific setup. There will be a lot of people out there who have a similar set up but there will be more who do not have the technology that I use. I could have users who are from India and who are on a slow internet connection. You may want to view my site on mobile, without having to rely on my creating a specific "mobile-native" version of the website.

There are a few factors that I took into account when designing this site for accessibility.

## Text

As much as I love pretty shaded text and nice backgrounds, I opted to use a high contrast color palette: black and white. All text appears in black, aside from links, which is important for reasons I will detail in a minute. This means that the average user should have no trouble reading my site. There are no faded gray colors that may be difficult to read. There's black and white.

I was tempted to add in a feature that would allow you to switch contrasts. I've seen a few websites do this in the past and I think it's a great idea. I'm not too sure about this but I believe there are certain color schemes which are better for different groups of the population. Building this would involve adding JavaScript to my site and so I decided against implementing such a feature.

I use all the appropriate HTML tags to represent text. <h1>, <h2> and so on tags are used for titles; all other text is enclosed within a <p> tag. I've been quite conscious about how I write the HTML for this site because screen readers are heavily dependent on what tags are used. A <h1> tag is much better than a <span> tag that has a larger font size. The screen reader, as far as I know, understands that it needs to emphasize a <h1> tag in a particular way.

I have opted not to use any fonts. My last site used Open Sans which I think is my favorite font. Who knew that I had a favorite font? It's just one that has cropped up quite often in my programming and so I have largely stuck with it. This site uses the default HTML font. There may be some people who find this difficult to read but I think it's worth the trade-off. Custom fonts are more likely to be inaccessible to users.

## Size

This is a lightweight site. I spoke in blog posts that I wrote for my old blog about how I felt my site was over-engineered. To make this site more accessible, I wanted to go back down to the basics.

Size is an important consideration for me because not everyone can render a large website. My site was never a megabyte in size anyway -- unlike all too many sites on the internet -- but I do know that every kilobyte counts. I encountered an interesting group called the Bandwidth Conservation Society. They were founded in the late '90s and advocated for smaller image sizes. It's not like they counted every byte on your site: they just wanted your site to be as small as possible so it could load quicker.

I have tried to include as little styles as possible on this site. You don't need to render a large CSS file to load any web page. Similarly, I have opted against using images, at least for now. The Bandwidth Conservation Society says that there are ways to compress images to a smaller size than the typical web image but I haven't investigated that just yet. By not including images -- and by including a small stylesheet -- this site should be fast to load.

## HTML Accessibility

I spent a little bit of time reading about HTML accessibility while I built this site. I'm going to call myself a novice because I bet there's so much more to explore. I did try to incorporate some of the basic learnings into this site so that it is more accessible.

The links on this site are all colored. This is the only use of color on the site. All links, except for my name in the top left corner of the navigation bar, have their default underlines. I have left these in place because they make it really easy to distinguish a link from the inline text of a page. It may not be as aesthetically pleasing as some of the fancy colors I used in my last site but it's definitely more functional.

All links, except those to other sites, come with a "title" attribute which explains what that link is. From what I understand, this is interpreted by screen readers in certain circumstances. This makes it easier to navigate around the site. The "title" attribute may be hidden to the average user but it is there for those who need it.

## The Big Test

I am going to test this site today using two test suites. I'm going to see what accessibility tests are out there and try one or two out. This will help me validate the code that I have written. I am also going to visit my site, once deployed, from w3m, the text-based browser I mentioned earlier. I want my site to be accessible to as many people as possible, irrespective of their devices.

While this is largely not a concern today, I have taken every effort to use basic HTML and CSS rules. This reduces the chance that a page will not render correctly on a different browser. JavaScript is not used because: (i) it takes up more space and; (ii) I want the site to be easily accessible to people who do not have JavaScript enabled (a decision I totally respect).

It's not as if I share the most interesting information in the world but I do care deeply about the user experience for this site. User experience, to me, means that as many people as possible should be able to use a site. That has meant going back to the basics. The purpose of this site is to give me a little home on the internet and to share some of my thoughts. No more than hypertext and some simple styles are needed to make this home. That's all I have used. I'll try to keep updating this site as I learn more about accessibility, and as my interests change.