---
layout: post
categories: ["Web", "Post"]
title: "Accessible Interfaces"
---

I'm not an expert in building accessible interfaces. I do not know much about ARIA other than that it is used for accessibility. I have come to learn that there's not much that I need to know about accessibillity if I let HTML do its job. I do not need to do much hand-coding for accessibility because most tags have already been built to promote access for all users on a website. As long as I use semantic tags, I'm on my way to having an accessible site.

I read an article yesterday on how sourcehut has built an accessible interface. They took a similar approach to the one I used to build this blog, although I must admit they are doing it at a much larger scale. The key to sourcehut is that they've tried to keep everything as simple as possible. Their website does not use JavaScript. They use plain text liberally. In simplicity, they have found that it is easier to create accessible interfaces.

The creator of sourcehut says that they only spent a few hours thinking about accessibility prior to writing the article. I spent a similar amount of time thinking about accessibility for this site. Well, I spent more time than that if you count the thoughts I had while journaling and such. When it came to implementing an accessible interface, I only spent a few hours doing it. This blog did not take long to build.

## Target Audiences

Different people have their own accessibillity concerns about the internet. I started to evaluate these independently yesterday to see how my site measures up. Accessibility checker tools are useful but I want to learn more about how to make conscious design choices. To do this, I need to consider what it is that accessibility really means. Who is it that my accessibility efforts should be catered toward?

One category of people are the color blind. These are people who can see but who may not be able to interpret colors like me. They may see only gray colors. I knew a man who had a condition that affected his sight in this way. The accessibility of websites can affect even those close to us. They may see some colors but not others.

I have recently changed the color scheme on this site to support the color blind. This site uses two colors: dark blue and orange. I used to use a light blue but it had a poor contrast rating. I decided to change it to a darker blue, although not the default. I am using custom colors only because they do not add context to the page. They are purely for aesthetics. I only use custom colors in places where it will not impair the user's ability to interact with my site. That's why I was so prompt in changing my color scheme for links. Links are crucial for all users. They need to be as accessible as possible.

There are people who are visually impaired to the point where they need a screenreader to interpret some or all of a web page. This is where writing a well-structured web page is handy. I have written as much of this blog as possible in semantic HTML. I did the same for ColdBrewLinks which I launched yesterday. I used `<article>` tags instead of `<div>` tags. If there's a semantic alternative to a `<div>`, I will try to use it.

Having a well-structured web page makes it easy for screen readers to navigate through a site. That's also why I am not too concerned about adding complex styles to this site. If information is presented side-by-side or in a way other than top-to-bottom, it becomes quite difficult to design accessible experiences. I have taken the simple approach. This allows me to deliver an elegant and accessible user experience.

## Browser Defaults

A lot of the elegance of this site is that I leave the browser to do a lot of the work. Remember, users can change settings on their browsers. A browser can use different default font sizes and settings. Adding in my own custom fonts from external sources would only mean that I'd be overwriting a user's preference. If a user has went to the lengths of configuring settings like fonts in their browser, it means they expect sites to uphold it.

I do use a font on this site. The font I use is "web-safe," or built-in. This means that you do not need to download any fonts to view it. I can deliver my web site more swiftly because I can reduce the number of web requests each web page makes. What's more, web-safe fonts were designed for accessibility. I know that the font that I use has been made web-safe for a reason.

I do not override font sizes. There are a lot of other settings I leave blank. Having custom rules for these features would only add more complexity to my site. I know that by letting the browser do what it is good at, rendering web pages, I can offer a more accessible experience.

## Speed

I've spoken about the relationship between speed and accessibility in prior blog posts. I have come to understand it from a new perspective. Speed matters even more for people who rely on accessibility features because they may take longer to browse the web. Whereas features like images give me visual context when I am viewing a site, there's no guarantee that all users can view these. It makes it more difficult to decide if a web page is valuable.

The quicker my pages load, the easier it is for users to make a decision about my sites. It's not just speed from a bandwidth perspective that matters. I like to get to the heart of the content as soon as possible. That's why I have a "Skip to main content" button at the top of every page. It allows users to view my content without having to read the entire navigation bar with their screen reader.

Most of the accessibility features on this site are provided by plain HTML. All I have done is decided to follow the grain of HTML. I am letting HTML do what it is best at without introducing added complexities like complex layouts or JavaScript. My main takeaway from the article on sourcehut is that it's much easier to design accessible experiences when you keep things simple. There's a design principle to which I can refer: KISS. Keep it simple, stupid. That may be the most apt philosophy I can use to describe this site.