---
layout: post
categories: ["IndieWeb", "Post"]
title: "Cleaning Up the IndieWeb Webring"
indieweb: true
indienews: true
---

I received an email yesterday from someone who has dipped their toe into the IndieWeb. They are not very active but they are a participant on the IndieWeb webring. This reminded me that the webring was what got me really interested in the IndieWeb. It is a directory of sites that adhere to IndieWeb principles. To be admitted into the webring, you must have a valid `h-card` on your website.

I have surfed around the IndieWeb ring countless times. When I was first beginning on the IndieWeb, I used the webring to see how other people implemented IndieWeb features. I encountered great diversity across sites. I have found that the best way for me to learn about IndieWeb principles is to implement them myself. I needed inspiration when I first started to get me going.

Over the last month or two, my mind has occasionally thought about how some links on the IndieWeb webring are broken. My friend reminded me of this issue. This is a natural part of having a webring. People change their websites. Some people will have removed their webring affiliation. Some people will have invalidated their webring after changing their website. Some people may have changed domains. 

I decided to write a script to clean up the IndieWeb webring.

## Retreiving Active Members

My first instinct was to use a library called Beautiful Soup 4 to retrieve all of the members from the site. This turned out to be unnecessary. I looked at the HTML for the webring and I noticed that it was marked up using microformats. I could use a microformats parser to see who is on the webring. This would be a lot easier than retreiving each individual domain name from the website.

I used the mf2 Python parser to parse all of the microformats on the web page. In only two lines of code, I was able to retrieve all of the microformats data on the website. I'm probably going to use this library again but I don't have any other microformats parsing needs at the moment.

With a list of all the websites, I had one more challenge. I had to check whether each active member was displaying a link to the webring on their site. My first idea was to check independently for either the "forwards" or "backwards" links. I ran into an issue with the Beautiful Soup 4 parser. That made me think of a more elegant way to solve the problem I was encountering. I used regex to check for any links to the webring.

I only check for links to the webring because there is a chance that a member may display the webring in different ways. I didn't want to check for all of the source code that is recommended that you add to your site. I only check whether a URL to the list exists.

I save two pieces of information about each site into a JSON file. This is the URL that I have checked and the status of that URL. The three available statuses are "active", "inactive", and "error". The third status was reserved because some sites timed out when I searched them. I learned that the `requests` module has a `timeout` attribute that lets me control how long a web request should take. This let me overcome an issue where my program would hang if a website took a really long time to load (which was the case if a site did not exist).

After I wrote the script, I added in a feature to tally up the results. I found that a total of 25 sites on the webring were inactive. I was only going to share my results if I found that there were enough inactive sites. My suspicions about there being more than a few inactive sites on the webring were true.

## Contributing to Open Source

I shared my script with the author of the project on GitHub. It's one of my first real "open source" contributions. I have a few ideas on how the webring could remove some of the older sites if they choose to do so. I wanted to write this script because I had an itch that I wanted to scratch. The itch was not in my own software but I knew that I could come up with a solution.

I wrote up a brief description about why this issue matters to me on GitHub. The webring is an important part of how I learned about the IndieWeb and I want as many people as possible to be able to benefit from its use. I tried to be as thorough as possible so that I did not miss out any important information. The more information I provide in the initial issue request, the easier it will be to discuss potential next steps.

This is not the most complicated program I've written. It did not take long to write. I did learn about how to use the `mf2` parser and I learned a few tricks with regex and the requests library. I'd much rather write code that has a real meaning than to build a project that I myself will not use. Over-engineering is only a problem when I solve issues that I don't have. I like self dogfooding. Or, as many people say, scratching my own itches.

You can view my issue request [on GitHub](https://github.com/martymcguire/indiewebring.ws/issues/7). The code I wrote for this project is in the issue request.