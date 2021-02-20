---
layout: post
categories: ["Coding", "Post"]
title: "Trying Not to Overengineer"
---

In a discussion with a friend, I mentioned how easy it is to overengineer solutions to problems. This weekend, I have been evaluating what it is that I want to do with my personal website. What matters most to me? In asking this question, I realize that I have been guilty of overengineering solutions to problems that may not actually be problems with which I should be concerned.

## Liberation as a Coder

Being a programmer means that I can fix a lot of the problems I encounter while using technology. I am going to use the example of my mirroring code to sourcehut, which is a project that I have failed to complete. The problem was that I was concerned about hosting all of my code on GitHub where there is only a single copy of my work. When I think about it, GitHub does have a history of restricting access to their services. If I remember correctly, there was somewhat of a tussle when people from countries (I think Iran and other locations) were unable to fully use their accounts.

I have been motivated to syndicate my code to sourcehut for a while. My first solution was a script that scraped all of my repositories from GitHub and created a mirror on sourcehut. I called this script [sourcehut-uploader](https://github.com/jamesgoca/sourcehut-uploader). There are ways I could improve the script but it worked to solve the problem I had: keeping a backup of my code. I was excited when I wrote this script because I would finally be able to easily syndicate my code. My script seemed a lot easier than setting up a new remote for every repository on which I work and committing code to both GitHub and Sourcehut.

This weekend, I changed my mind on my approach. I forgot about the fact that I had to *actually run* my program for it to work. I considered a cron job but I never got around to setting it up. That made me wonder what I could to to automate the process. Enter the second solution: webhooks.

## Overengineering Solutions

Webhooks seemed like a more reasonable solution to my problem. I can set up my GitHub repositories so that whenever I push a commit, a webhook will be sent to a server. This server can pull the new version of the repository and mirror my code to sourcehut. I spent a few hours yesterday getting this script to work. I had one main endpoint that listened for messages, pulled my code, and pushed it to the mirror of the repository on sourcehut. The process I used let me maintain the same commit histories. sourcehut was just a mirror; GitHub was my main line of development.

Last night, I asked myself a question that I've been avoiding for a while: do I need to solve this problem? The answer, at least right now, is no. I do not need to create a mirror of my code. I've seen a few of my IndieWeb friends have Gitea repositories or other places where they host their code. That was part of what motivated me to work on this project. I have come to realize that those people have their own itches. I share itches with other community members but this is not one that really matters to me.

See, when you can build a solution, it's so easy to go out and build it. I can write a program that mirrors all of my code to sourcehut. I had great fun doing it. I have [posted my code on Github](https://github.com/jamesgoca/sourcehut-mirror/) if you are interested in setting up a mirror. It works. All you'll need to do to get it running on your own infrastructure is change the name of the folder in which the mirroring should take place on your local machine. I am probably not going to deploy the code because it solves a problem I do not have. I do not want to have yet another script in the cloud to worry about.

## The Breaking Point

What made me realize that I needed to stop was that I spent quite a bit of time yesterday setting up a Flask server on my web server. It did not go well. I had to install Nginx and that conflicted with the Apache installation I have for my website. I use Apache because it is great for static sites. Both of these packages use port 80 by default. While I could change the port numbers, that would add another variable to the list of factors I need to consider when I write my configuration files. I determined it was not worth it.

I was not having fun with the server configurations. I can, and do enjoy, working on the command line. That's just part of being a developer. I now know that I do not enjoy deploying services to the cloud. My perspectives on this topic may change. It's just that I prefer to do the coding and the optimizations. The deployment is something that is a bit far out of reach for me. I know how to build websites but I'm not as strong at deploying them. I can get by with the deployment skills I have. I'm just not as confident working with deployment.

I am going to overengineer a lot of scripts in my time as a programmer. It's just so tempting. I get excited when I work on a software project. I like writing down all the issues I have to fix and going through them all in one swoop and fixing them. It's fun. The work is only enjoyable if I am doing it for a purpose. My sourcehut mirror was an interesting project but it solves a problem I do not have.

I am at this point with a few of my web projects. I am considering whether to set up a Flask server on which to store my [quantified self data](/fitness/). I have not yet started the project. It has taken a lot of willpower to resist opening Sublime Text and starting work. Oh how much I love setting up a new Git repository and doing the initial configuration for a project. But I realize that setting up that server will mean I'll have more to administer online. I want to keep my website simple. Hosting a separete site for quantified self data may be a bit too far.