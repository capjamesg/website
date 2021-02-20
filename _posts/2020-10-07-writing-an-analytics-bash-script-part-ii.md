---
layout: post
categories: ["Technology", "Post"]
title: "Writing an Analytics Bash Script: Part II"
---

My first attempt at writing an analytics bash script got me excited about bash scripting. My first script displayed the total number of page views my blog receives and the total number of people who have viewed my feed. The program was limited to reading logs for the last two days.

My goal with writing an analytics bash script was not so much to learn about my site but to build my skills. I'm not necessarily interested in tracking how many people view this website every day. I'd just like the option to check for this information if I get an urge. I have not researched existing packages extensively but I do know that most analytics tools offer more features than I need. I want a simple solution.

## Searching Past Logs

Nginx zips a day after that log is written. This presented me with a problem. My initial script did not unzip files. It only read plain-text log files. I had to unzip files before I could see the overall statistics for my website.

I wrote a series of commands that copied my logs into a new folder and then unzipped them. I copy the logs into a new folder because I did not want to override my existing log files. I read that one of the unzip commands I was considering would replace the original file. I did not want to take any risks. I created a folder in my home directory where I store my past logs for the purposes of running my bash script. This folder is cleared after the script has run.

I used the `gunzip` command and a for loop to unzip every file in the directory. This gave me the plain-text files I needed to see all of my logs.

## Displaying Popular Pages and Posts

My command line utility only displayed how many views my site and RSS feed had received. This was a good introduction. My first script helped me break the ice with bash. This is definitely the biggest project I have taken on. I needed to work slowly. I decided that I wanted to see all of the most popular pages and posts on my website. I do not intend to change my blog based on what I found. I am just curious about how people navigate my website.

I spent a long time writing a command to display the most popular pages. I used `awk`. This command let me retrieve the names of all of the pages that appear in my nginx logs. awk lets me split up my file and reference values by column. The URLs that visitors have seen are in column seven. I also used awk in a later command so I could see only pages whose URLs included `/2020/`. Posts that contain `/2020/` are blog posts.

I used the output of the awk command to find how many times each line occured in the file. The `uniq` command finds unique lines in a text file. I added the -c flag to calculate how many times each line appeared. This gave me a tally of how popular each file is. I use the `sort` command to sort this information. The `head` command lets me retrieve only the top five results.

I wrote three commands using awk. One command retrieves the most popular pages. One command shows me the most popular blog posts. Another command displays a breakdown of the status codes that have been served by my web page. These were the only pieces of information I wanted.

## Resisting Complexity

I was close to expanding my script. I had a lot of fun writing in bash. I have learned that bash is a really powerful tool. What surprised me about bash is how I was able to write my analytics script using so few lines of code. My script is 56 lines of code. This includes comments and whitespace. I was tempted to write this script in Python. I probably would have used at least 100 lines of code to write this analytics script. 100 lines is a conservative estimate.

I was going to add command flags which let me filter my logs. A flag could let me display only the top ranking posts, or only the number of people who viewed my site. I would have to use a new command to interpret arguments. This would make my script more complicated. What I have at the moment works. I do not need a comprehensive analytics tracking package. I want a bit more visibility into how many people view my site. That's all.

I have tried to make my code as readable as possible. I'm still learning about bash. I did split up some of my commands using line continuation characters. Apparently I did not save this change. I have just amended my script to use line continuation characters. In my research, I came across a few scripts that were so difficult to read. I've tried my best to keep my code simple. I didn't introduce command flags because I am not ready. I'm going to take my journey to writing more shell scripts step by step.

I must say that I do not have any other itches that I want to scratch. I'll find an itch at some point but I am not going to push myself. I don't want to write code that I am going to abandon a few days later. I want to write code that lasts. I'll wait until the right idea comes along.

You can view my new analytics script on [GitHub Gists](https://gist.github.com/capjamesg/641fe600ebb58389a52ad4199eed2d4c).