---
layout: post
categories: ["IndieWeb", "Post"]
title: "Owning My Coffee Data"
indienews: true
indieweb: true
---

The IndieWeb is all about scratching itches. When I think about what I want this site to become, I often say to myself that I am building a home for myself on the internet. Starting on the IndieWeb, this was enough. I needed to let my creative spirits run wild. I needed to try out different ideas. I looked at other people's websites and thought about what I could implement.

Could I do RSVPs? Do I even want to? These are the sorts of questions I've been asking myself. I do not know everything that I want to share on this site but I am confident of two pieces of information that need to live here. First and foremost, this is a place for my writing. I try to write a blog post every day. I love writing. I want my writing to be accessible to anyone. That's what the web is all about: sharing what I create.

I have a secondary itch that this site should scratch. I should be able to display my coffee review data.

## The Significance of Coffee

Over a month ago, I started to take a keen interest in coffee. I have two bags en route as we speak, both freshly brewed. One is from a local roaster. Exciting. My delivery schedule aside, coffee data is important to me. I try to take notes on as many cups as I drink as possible. I do so because it lets me see how my journey is unfolding.

I haven't yet gone back to previous entries but I expect I will in the future. I often find myself saying that a coffee reminds me of another cup I have consumed. I can go back to notes if I need to so I can make a stronger link between what I am tasting and what it is that I got out of the cup of which I was reminded. Coffee is one of my hobbies at the moment. I treat all my notes carefully.

## Sharing Data on My Site

I have decided to share my coffee journey on my site because I think the data is interesting. While it's unlikely that every visitor will be interested in my thoughts on each coffee that I drink, I can use my coffee log to share brews that I am particularly proud of or that I feel tasted great. I had a conversation with a friend over email a few days ago where I linked to an image hosted on Airtable of a latte I recently drank. I would have felt more confident sharing an image to my website but, at the time, I did not have one.

The first version of this project involved writing a Jekyll plugin to retrieve data from the Airtable API. The data was displayed on a table on the `/coffees/` page of this website. To start, this worked fine. I have been writing more reviews and it has become clear that this approach no longer works. The page was growing significantly in size because I sometimes write multiple paragraphs about each coffee that I try. I needed a new approach.

I was frustrated with having to make another API call every time I built my site. Making an API call and retrieving data has a noticeable impact on the build time for my static site, moreso than adding new files or updating existing files. It was a small concern but one that I have been thinking about actively over the last few days. I want to reduce the number of API calls I make to build my site.

## The New Approach

It was time to rethink how I shared my coffee data. I have scrapped the table structure and opted to create individual pages for each coffee. I was concerned that this would add to the size of my site but after doing some testing it appears that my new approach will not have significant impacts on the build time of my website, at least for the foreseeable future.

To determine this, I created 200 files with some basic content and added them into my project. I found that the build time only increased marginally. Each file was a copy of my `podcasts.html` file with a different permalink so that I could get a real sense of what build times would look like. Confident that creating individual files for each review would work, I decided this was the right approach.

My coffees page now displays a list of all the coffees I have consumed. This information is no longer presented in a table. Each coffee links to an individual markdown document with my review. This review contains the name of a coffee, where I consumed it, among other pieces of data. [^1]

## Using Microformats

Each individual review is marked up using microformats. This means that my coffee data will be easy to process should I ever choose to do anything with it. This was a big reservation I had about mirroring my reviews from Airtable to my own site. What happens if I want to analyze my data? With microformats set up, I'll be able to use the mf2 Python parser to view my data.

I have used the h-review specification to mark up my coffees. On my `/coffees/` page, I have created a h-feed that contains links to all of my h-reviews. These links are created using nested h-reviews. I am unsure what I will do with my h-feed just yet. I am still new to microformats. I have a lot of reading to do. The forum has been a good source of information to aid me in my journey. I've always got the IndieWeb chat if I have any questions.

## The Structure

My reviews are stored in markdown files in a separate folder in my Jekyll project. Here is an extract of my project structure:

```
index.html
projects.html
_posts/
_coffee/
assets/
...
```

Individual files are denoted by their extension. Folders with an underscore are locations of collections. In my `_config.yml` file, I have defined "coffee" as a collection. This lets me access a list of the files in the `_coffee` folder using the `site.coffee` variable in front matter. The markup for my coffee collection in my config file is as follows:

```
collections:
  coffee:
    output: true
    permalink: /coffee/:name
```

The permalink attribute lets me define a unique location for each file on my website. I have chosen to use :name, which represents the name of each file. For convenience, the names of each file correlate with their ID in my Airtable database.

I am confident storing my data in files because files have the greatest chance of long-term survival. Whereas databases can easily crash or get corrupted or become inaccessible, files stored in plain-text and markdown formats are less suceptible to these issues. I am forming an opinion on the great IndieWeb database antimatter debate. I think that data, when possible, should be stored in files.

I want my site to be accessible for as long as possible. Even if it is not online, I still want to have my own archive of the data. This archive has to be standardized and easy to navigate otherwise it will serve little purpose. Combining microformats, the static website philosophy, and a clear structure, I believe I have achieved this goal. It is an iterative process. I've still got to think through the implementation details for many of the other itches that I want to scratch.

[^1]: I have obscured the names of the places where I consume coffee for privacy. Each cafe or home brew shares the same name for consistency but I will not say what codename maps to which cafe or home brew.

