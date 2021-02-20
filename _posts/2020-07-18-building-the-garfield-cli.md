---
layout: post
categories: ["Coding", "Post"]
title: "Building the Garfield CLI"
---

I decided that I would work on a side project earlier this week. I enjoy hacking together tools in my spare time, but I only ever do it when an idea strikes. An idea came to mind and so I decided to build it. The idea was for a [Garfield command line interface](https://github.com/jamesgoca/garfield-cli).

Around a week or two ago I discovered a site called [Garfield Light](https://ermel.org/garfield.php), hosted by Ermel. The site shows Garfield comic strips through a stripped-down user interface. The page loads the comic strip and a few lines of text. I can see where the tool gets its name. I used to read the Garfield comic strip when I was young and with my grandparents. It has a special place in my mind. I wanted to do something with what seemed like a promising tool.

The Garfield LIght interface allows you to search through the archives of the comic. You can view any comic in its archive. I started to wonder what I could do with this information. I decided that I wanted to create a command line wrapper for the project.

The command line does not download or open any comics. It takes you to the Garfield Light site where you can view a comic.

## Getting Started

I first started by defining the scope of the project. What did I want this command line to do? I wanted to be able to see the latest comic, search the archive, and find a random comic. I do not read comics often but there are some days where I like to read a few strips. On those days, having a random feature would be incredibly useful. For every other day, having a command to get today's comic strip is just what I would need.

The initial version of the project was written using the Python shell. I was not sure how to build a command line interface and I just wanted to get the tool working. I used the webbrowser package that comes built in to the Python language to help me open web pages. A lot of the work I needed to do was on the data validation side. What if a user tried to search the archive for a comic that did not exist? How could I get yesterday's comic by date?

I managed to overcome these problems and come up with a simple solution. When you run the Python shell version of the script, you are asked to insert a number. That number corresponds to a series of commands. The one feature that the shell version does not support is choosing a comic from the archive. I am going to build this later today. I forgot about it until now. This interface does not have many bells and whistles. It works just as I need.

## Building the Command Line

I have built a command line interface in Python. I could not for the life of me remember how to do it. In my research, I discovered a package called click which allows you to build CLIs in Python. It is really intuitive. There were a couple of issues that I encountered. Those were on account of my lack of experience using the tool. The tool made it easy for me to turn the shell version of my code into a command line.

I started by copying and pasting the code from the shell version into the command line version. My mind then started to notice that I was repeating a lot of code. What if I wanted to make changes to it? I would have to replace two separate instances of the same code. That's when I decided to write a garfield module. This module contains all of the code needed to run the tool.

Both the shell version of the command line and the command line interface use the same module. This helped me reduce redundancy in my code and create a cleaner codebase. I haven't written a lot of modules in the past. This seemed like the perfect opportunity to build one. I am now happy that there is very little, if any, repetition in my code. The readability of code, to me, is just as important as its function.

## The Launch

Once I had a functioning version of the command line ready, I started to work on all the post-project tasks. I wrote a better README.md. I even added a license to my tool. I do not usually do this but I thought it would be best. I want people to riff on my code and use it to build their own tools. I uploaded a screenshot of the project to the README.md file.

The Garfield CLI is available on my [GitHub](https://github.com/jamesgoca/garfield-cli). I am making a few changes to it. I will be uploading it to PyPi so that you can install the garfield command on your computer without compiling it from source. I am not sure whether people will use the tool but I will. I no longer need to navigate to my web browser and search up the Garfield Light interface. I can open the comic from my terminal. A web browser then opens with the respective edition of the comic.

A few learnings stood out from this project. The first is that writing readable code is really important to me. I took great care in ensuring that every line of code made sense. I took the same approach as I did when I built this website: the fewer lines of code I could write, the better. The second learning was that building side projects is fun, but only when I have the ideas. I build when my mind is active; I think the rest of the time.

To all of you Garfield lovers who love the command line, this tool is for you!