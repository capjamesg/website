---
layout: post
categories: ["Technology", "Post"]
title: "Writing an Analytics Bash Script"
---

I have had a commitment to not track analytics on this site. I believe that tools such as Google Analytics are verbose. They track too much information about users. I do not intend to change my policy on this matter. I did see on the IndieWeb wiki and on GitHub that some people have built their own analytics tools. Many of these rely on the logs that are collected by a web server rather than on a client-side script.

My research got me thinking about how many people look at my RSS feed every day. I was curious and I was not able to let this go. I don't expect many people read this blog but I did want to see how active my feed was. I decided that the best way to do this would be to write a short script that looks at my nginx server logs and counts how many views my RSS feed has received.

## Choosing the Technologies

I was tempted to write my tracking script using Python. I have more experience with Python than any other programming language. I knew exactly how I would retrieve and process the data from the nginx access log. My mind was making plans. I thought about how I would parse files so that I could calculate analytics such as the highest ranking pages.

I decided that a bash script would be better. I remembered that there is a command called `wc` that would help me out. This command lets me see how many words appear on a document. The command also displays the number of lines that exist in a file. This in itself would let me see how many people had visited my site. Each line in my nginx server record represents a unique page view. The issue was that I would not see how many people saw the RSS feed.

## Using Bash Commands

I played around with a few commands. I used the wc command to calculate how many page views my site received. I then thought about moving all of my commands into a script. This would be necessary because, as I later discovered, nginx stores access logs in different files. This means that I would need to use a loop to view all the files. [^1]

Writing a bash script let me move all of my code into one place. I set out with a simple goal. I wanted to calculate how many people viewed my site and how many people viewed my feed. I already had the command to see how many people had viewed my site.

I used the `grep` command to retrieve all the instances of `feed.xml` in my nginx logs. This let me see all of the lines where the string `feed.xml` was present. I used the `-c` flag with the grep command to cound how many times that line of text appeared. This gave me the second piece of the puzzle.

Nginx separates out access logs by day. A new log file is created each day. I wrote a for loop that went though all of the files beginning with `access` in the nginx log folder. I enclosed my grep and wc commands in the loop. I then created a simple counter that counted the total page views and feed views across all the log files.

My final script looks like this:

```
#!/bin/bash

page_view_counter=0
feed_counter=0

for f in /var/log/nginx/access*
do
	((page_view_counter+=`cat $f | wc -l`))
	((feed_counter+=`grep "feed.xml" $f -c`))
done

echo "Total Pageviews: $page_view_counter"
echo "Total Feed Hits: $feed_counter"
```

## Learning About Bash

I did learn a lot about bash. A big reason why I don't want to write a Python script is that bash itself is really powerful. Bash may not have all the features I am looking for. I feel that I am learning more this way. I am having to push the boundaries of my knowledge.

I learned that arithemetic operations must be enclosed in curly brackets. I learned I could iterate over a list of files without having to use the `ls` command if I specified the file path as part of a for loop. I'm still learning.

This script is simple. I do have plans to add more features. I'd like to see the top-ranking pages on my site. My mind has been thinking about how I would implement that feature. I do not want to create a big dashboard to display these metrics. I'd just like the ability to see how my site is doing when I am interested. I'll keep this script on my server so that I need to log in to run it.

Working on this project has made me feel more confident in choosing the right technologies for the job. I could have written this script in Python but I wouldn't have learned as much. I do not know much about bash. This is a learning opportunity.

I have discovered that bash is really powerful. The piping feature lets me use the output of one command with another. This is what gives me confidence that I'll be able to write my entire script in bash. There are so many UNIX commands that there should be at least one that offers me the features that I am looking for.

[^1]: I later learned that old access logs are zipped. I am not yet at the point where my script unzips these files. I can only see logs from the last two days without unzipping any archives.