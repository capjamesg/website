---
layout: post
categories: ["Web", "Post"]
title: Writing a New Tab Extension
---

Writing an extension for Firefox has been in my mental to-dos for a while. I like the idea of having my own new tab page. I used to use an extension called Momentum which displayed a nice image alongside the time. For my purposes, Momentum was a bit verbose. Every time I loaded a new tab, I had to render an image. Sometimes it took a second for that image to render. There were many customization features that I did not need.

Earlier this year, I looked into how I could write a new tab extension. I was discouraged because I couldn't find a good resource on how to write an extension. Most of what I found was extensions people had written that let you replace your new tab page. I wanted to write an extension to replace my own new tab page, not rely on another extension to do it for me. I left the idea for a few months.

## A Home for My Browser

I came back to the idea a few days ago. After doing some research, I found out that writing an extension was within my reach. A browser extension can be as simple as a HTML page with a file called `manifest.json`. This file provides the configuration for an extension.

My intentions for the new tab extension were to keep the design as simple as possible. I wanted to display the time but not in a way that takes up the entire middle of the web page. I wanted to have a friendly message that said "hello" to me whenever I open a new tab.

What inspired me to work on a new tab extension is that I've been in a bit of a, for lack of a better word, pickle, since new lockdown restrictions were announcd in the UK. I came up with the idea of making a web page that lists all the fun activities that help me stay positive. I decided that this may be a bit much for me to take on. A new tab extension would be simpler.

## Getting Started

I started simple. The goal was to display my name and a hand-written message on my page. To do this, I created an `index.html` file and modified its contents. I was not thinking about how to bundle my extension or install it into Firefox. I just wanted to get a page working. I created a `styles.css` file for the style sheet and I thought about what aesthetic I'd like to use.

This project is supposed to be simple. That's why I went with a simple design. I took inspiration from my blog and gave all of the headings colors and a colored underline. [^1] The background remained white. I used a web safe font so that I would not have to load a new font every time the page loaded. That was it. To make the page a bit nicer, I added in a countdown to my birthday and International Coffee Day. They are the same day.

This counter was not operational yet. I was fine manually changing the numbers. I just wanted something that looked good so I knew what final details should be implemented on the new tab extension.

## Writing the Vanilla JavaScript

The new tab extension is powered by some vanilla JavaScript. I'll need to go through my code an optimize it. My code works for now. The first feature I added was a clock. Every second, a function is executed that retrieves the current time. That function updates a `<span>` tag on the web page. This lets me display a functional clock on the web page. I did consider updating at different increments but this would not work. If I updated the page every minute and the user loaded the page at XX:59, the minute counter would not update until the next minute had passed. The clock would be off.

I then added a countdown to my birthday and International Coffee Day. I'd already written the HTML. I just needed to write the JavaScript. This proved to be somewhat of a challenge. I needed to find the difference between two days. Once I had found the difference, I needed to make sure that the text on the HTML page was gramatically correct. "There are 1 days" does not make sense, but "There is 1 day" does. I had to support this functionality in my code.

The final feature that I added displayed a quote on the page. I am proud of the code I wrote to support this function. When the new tab page is loaded, Firefox checks for a value inside the Firefox extension storage. This value contains the Quote of the Day taken from [quotes.rest](https://quotes.rest/), a REST API that stores quotes. If the quote is not saved in local storage, I call the quotes.rest API and retrieve a quote. This quote is saved in local storage.

This means that I don't have to retrieve the quote from a web API every time I load the page. This helps me keep my extension lean. Loading a HTTP request every time I open a new tab is not convenient. I also found out that quotes.rest has a rate limiting feature (which is no surprise given they are an API). I'd easily hit that rate limit if I kept opening new tabs. I open new tabs often, especially when I am working.

I save each quote alongside the date on which that quote is retrieved. If there is a quote in local storage, my extension checks whether that quote was retrieved on the same day as I am viewing the page. If yesterday's quote is still in storage, a new quote is retrieved.

## A Small Project

I'm going to keep this extension simple. I had visions of creating multiple browser extensions. One would show the time in a way like Momentum, without all of the features that I don't need. Another extension would display stats from the IndieWeb wiki. This is a classic case of planning out work that I don't need to do. I can only have one new tab page. I am happy with the one that I have.

![A photo of my new tab extension](/assets/new_tab.png)

The design is simple and I like it that way. The color makes me feel happy. The countdown reminds me of the exciting events to come. I'll probably manually change the birthday countdown to a Christmas countdown later this week.

I feel much better now that I have a more aesthetically pleasing new tab extension. I haven't signed the extension or released it into the public over the Mozilla App Store. It only runs in the Firefox debugging environment for now. I do want to make my extension run as an add-on rather than a debugging add-on but I am having a few issues. I'll come back to this when I am ready.

[^1]: The colored underline is a bottom border because I cannot change the color of the `text-decoration` property as far as I know.