---
layout: post
categories: ["Coding", "Post"]
title: "Stand Up Notifier"
---

I've started to do some reading on how to work sustainably at a desk. My recent tidy up of my work environment is probably what has me thinking about this. One of the ideas I've noticed is that I should get up and walk every so often.

In the manner of an engineer, I decided to approach this from a technical perspective. My goal was to create a program that reminds me to stand up every hour. I hope this will encourage me to get out of my chair and get walking.

## Building the Notifier

The script I have devised is simple. It relies on the [terminal-notifier](https://github.com/julienXX/terminal-notifier) macOS package. terminal-notifier lets me send notifications to my desktop from the command line.

I have created an entry in crontab that sends me a reminder to get up every hour. Here is the command I have written:

```
echo "Stand up for a few minutes." | /usr/local/bin/terminal-notifier -title "Stand Up"
-appIcon "/Users/James/Downloads/walking.png" -sound default -ignoreDnD
```

I downloaded an image of the "person walking" emoji from the internet so that my notification looks a bit more enticing. By default, the Terminal application icon is displayed. 

## Setting up Crontab

I have learned a bit about crontab through this small experiment. First, I learned how to change the crontab editor. I do not like vim as it is confusing. I prefer nano. I learned that I can override the default editor by exporting a VISUAL parameter in my session:

```
export VISUAL=nano;
```

In any session where that environment variable is present, `nano` is used as my editor. Next, I learned (for now) how to create a crontab job that goes on every day. I'll probably forget but it is an easy one to remember: `1 * * * *`. 

When I started writing this article, I wanted to view my crontab. I found out that I can use `crontab -l` to view my crontab. This saved me from having to use redirection or the `cat` command or another approach to view my crontab in the console. I could have just opened the crontab for editing but I wanted to know how to open crontab for viewing only.

## Being Active

I am conscious that I am not sitting in the best position as I write. It's going to take a long time for me to get out of my posture habits. I'm so used to sitting in this chair in a certain way. I'm hoping that this new notification will encourage me to get up and walk. The barrier I foresee is that when I'm working on something I often get too immersed in the work itself and do not want to stand up. Maybe I will need to create a more advanced script further down the line that hides my windows. I'll see how this one goes first.


