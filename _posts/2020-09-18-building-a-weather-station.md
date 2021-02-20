---
layout: post
categories: ["Web", "Post"]
title: "Building a Weather Station"
---

At this week's Homebrew Website Club meeting, we had a discussion about Raspberry Pis. Most of the people in attendance had a Raspberry Pi. We all showed each other our Pis and where we had them set up. It was fascinating. I had to admit to everyone that my Pi has been sitting lonely in a drawer for a while. I haven't done much with it. I have a Sense HAT. The Sense Hat sits on top of the Pi.

This meeting made me think about what I could do with my Pi. I racked my brain and arrived at the idea of a personal weather station that reports on the weather to the internet. I love working with data so this idea seemed like a match made in heaven.

## Retrieving Data

The weather station retrieves data on the temperature in my room and the temperature outdoors.

To gather the temperature in my room, I use the Sense HAT. I have configured a script to collect the temperature, humidity, and pressure inside my room. This script writes the data that it collects to a file called `data.json`. I write this data to a file so that I don't have to check my Sense HAT every time someone loads the web server page. This would be burdensome and add significant complexity to my project.

I have a crontab entry that runs this script every hour. This means that my data is not real-time but it should give you a good idea about the environment in which I am working or spending time.

The temperature in my room is not representative of the full environment around me. The outdoors matters. I spend quite a bit of time outdoors when I am not working. I use the OpenWeatherMap API to collect weather data for my current location. I report on the wind speed, the temperature, and a few other metrics that are most relevant to my environment. This data is part of the web server which I'll talk about in a minute.

Combined, this data paints a picture of my environment. If it is really warm outside, you'll probably know that I will want a cold brew coffee. If it is really cold indoors, you'll be able to assume that I will be wearing a robe or a blanket to keep me warm.

## The Web Server

This project would not be complete without the web server. I wanted to make my data visible so that the rest of the world can see my temperature. I do not think this information is useful to most. I would struggle to find a real use of this data. I do find it interesting and cool so I built this project. That's what motivates me to build a project: if something is cool, I will build it.

The home page of the web server displays the latest data from my weather station and from the [OpenWeatherMap](https://openweathermap.org/) API. Every time the page loads, the OpenWeatherMap API is queried. This means that you'll get a real-time report of the current weather in the place in which I live. I retrieve the contents of the `data.json` file that my Sense HAT script generates and read the contents of the last record. This record contains the most recent entry.

On the web page, you'll see all of the data that I collect presented. I added a feature where the background color of the page changes depending on the temperature. To do this, I used a jinja2 if statement inside a CSS rule:

```
<body style="background-color:
	[% if color_temp <= 2 %]
	midnightblue
	...
	[% else %]
	lightsalmon
	[% endif %];
">
```

*Note: Substitute the `[]` characters for `{}`. Jekyll did not like me adding in templating syntax in the code snippet.*

This code is not the most elegant I have written but templating syntax is rarely as clean as I would like. If it is cold outside, the background color of the page will be a dark blue. If it is warm outside, the background color will change to a salmon color. This color is a good shade of orange for a background. This was inspired by Low-Tech Magazine's solar-powered website. The background of their site changes depending on how much battery is left in the power source connected to their Pi.

The web server feeds out some statistics about the server itself. You can see how the system is performing at the `/stats` page. I may use this data to make sure that my server is running at a good temperature and has enough storage space. I am presently using an 8GB SD card for my Pi. I ran out of space this morning and so I have ordered a new, big, 128GB SD card. It was on sale and I thought I'd just buy one.

## Raspberry Pi Projects

I do enjoy working with my Raspberry Pi. Earlier this year, I spent some time making pixel art with the Raspberry Pi. I am tempted to explore the world of self-hosting. A friend of mine hosts their own Gitea instance from home. This gives them full control over their source code. I'll probably not do this because I do not have the room to install very many more dependencies on my Pi as it stands. I may give it a try later.

The Pi is a remarkably fast and lean computer. I have a Raspberry Pi 4 and I've not run into any performance issues. Out of an abundance of caution, I have ordered a Pi with a thermal case because I have heard the Pi 4 can get quite hot. If that's ever a concern, I can always check the system stats data on my weather station.

You can find the source code for this project on [GitHub](https://github.com/jamesgoca/weather). For this project to work, you'll need to have a Raspberry Pi Sense HAT. Let me know if you have trouble installing and setting up the web server. The weather station is still very much a work in progress. You can view my weather station at [weather.jamesg.blog](https://weather.jamesg.blog/).