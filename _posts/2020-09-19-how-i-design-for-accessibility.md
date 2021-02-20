---
layout: post
categories: ["Web", "Post"]
title: "How I Design for Accessibility"
---

I just finished an accessibility audit on my site. There is only one flag that is raised by Axe, the accessibility validator I use. I believe I can ignore that flag. It relates to the arrows that I use for my webrings. I do not believe the suggestion impacts the quality or accessibility of my website. I am proud to say that I've resolved many accessibility issues over the last few weeks.

This website is the first project where I've thought about accessibility to the extent that I am today. I've never really thought about how other people see my creations. I've always thought about how I consume what I make. This is normal. I like to eat my own dog food. In other words, I build the tools and websites that I need myself. This site is different. I want other people to read my content. The whole point in having a blog is to let me share my thoughts with the world. I want people to be able to read those thoughts.

I went down the accessibility rabbit hole about a month or two ago. I have read quite a bit on the topic. After doing some reading, I have more conviction than ever that accessibility should not be an after-thought. It needs to be a central part of my design.

## Testing for Accessibility

A friend recommended a tool called [Axe](https://www.deque.com/axe/) to me. This tool validates HTML code from an accessibility perspective. The tool checks for issues like poor color contrasts, invalid HTML, and incorrect markup. Axe is a browser extension so I can easily run it on any page. I was initially apprehensive about installing yet another browser extension but this one proved to be worth my time.

Axe takes a few seconds to analyze a page. Once the tool has analyzed a page, I am presented with a list of suggestions on how I can improve my code. My goal is for every page to validate without any issues. I have achieved this goal on all of the pages I have checked, bar the one insignificant suggestion I mentioned earlier. It's become almost a game for me. The more issues I can resolve, the better I feel about my website.

Most of the suggestions that Axe has made are small changes. I believe this is because my site is primarily HTML. I do use Jekyll to build my site but I don't use any JavaScript on the front-end and every web page is static. I don't embed any content from other sources. I don't have any scripts running. This massively simplifies the process of optimizing my site. I've just got to look at my HTML structure and my CSS styles.

What I've learned in using Axe is that most accessibility issues are the result of not using the correct semantics. When I use tags like `<header>` and `<nav>` correctly, I don't get any errors. When I use `<div>` tags in places where there is a semantic alternative, I start to see problems. It's amazing how accessible HTML is out-of-the-box. I just need to learn the semantics.

##Validating My Code

I use a [command line tool called `html5validator`](https://github.com/svenkreiss/html5validator) to validate my HTML code. I believe the tool uses an engine similar to the W3C markup validator. I use this tool to check for semantic issues in my code or areas where my code is incorrect. When I run this tool earlier today, I caught a few tags that I had not correctly closed on my site. These mistakes would likely cause accessibility issues on my site. For instance, there was an element that did not have a closing </a> tag. A screen reader would have read out more content than it needed to because I forgot to close the tag.

Validating HTML code is easy to do. I'm still trying to make it part of my workflow. I do not validate my code after every change I make to my blog but I probably should. I'm getting better at remembering to validate my code.

## Reading About Accessibility

To accompany the validation tools I use, I have spent some time reading about accessibility. A good recent read was on how to write "alt" attribute descriptions for images called "[How to write better alt-text descriptions for accessibility](https://bighack.org/how-to-write-better-alt-text-descriptions-for-accessibility/)". The post highlighted that I was not writing good "alt" attribuet descriptions. I was saying "A photo of" at the start of almost every description. Screen readers already know that an image is an image and they indicate so to their users. I don't need to say that an image is a photo of something in an "alt" attribute.

I went over all the images on my website and checked to make sure they had an "alt" attribute. If they did not, I added one. I checked to make sure that each attribute accurately and concisely described the image with which the attribute was associated. I found this was not the case in most instances. I referred back to the blog post on how to write "alt" attribute tags and made a few improvements. My images are now easier to consume for people who are unable to view them.

I'm just reading as I build this website. Earlier today, I read about how to write accessible tables. I learned about the `<theader>`, `<tbody>`, and `<tfooter>` tags that are used to write semantic tables. HTML gives me all the tools I need to make an accessible experience. It's just a matter of learning how those tools work. I am proud to say that my new "Wishlist" page includes a table that is accessible. I looked up how to write better anchor text to make sure that the links on the page are optimal for visitors who use a screen reader to navigate through my site.

One surprising fact I learned is that header tags should appear in descending order. Every `<section>` should have a header tag and it's improper to skip a tag. I can use a `<h3>` on a page but only if I use a `<h2>` and an `<h1>` first. I should not skip tags. I made this mistake on almost every page about a week ago and I had to go correct it.

Accessibility is going to be a long-term project for me. My new weather station application is accessible. This website is accessible as far as I can tell. I'm yet to do a test where I actually use a screen reader. I've not had the time. I am still learning about new ways to make my site accessible. The "Skip to main content" and "Go back to top" anchors on each page were the first accessible feature I really thought about adding. Now I realize that there are so many cogs that go into providing an accessible experience.

I've been able to get this far because I have asked the question "how can I make this site more accessible?"