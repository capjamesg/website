---
layout: post
categories: ["Technology", "Post"]
title: "Tracking the Word Count on My Blog"
---

I check the word count after I have written every blog post. I do this because Typora, the markdown editor I use, displays a word count in the top left corner of the page. I'm not interested in the metric. It is difficult to avoid. At some point yesterday, my mind arrived at the idea that I should try to track the word count on my blog. I wanted to do this to improve my programming skills.

I decided that I would calculate the word counts on my blog using bash. I have been using the `wc` command for a number of my recent scripts. It is easy to use and can be combined with other commands. I could have written this script in Python. That would have involved opening every file on my website, reading its contents, splitting words into an array, and calculating the length of each array. That is too much work for this short project.

## Calculating Word Counts

My first goal was to calculate the word count of each post on my blog. I wanted a total of all the word counts on my site. In the first version of my script, I used the `find` command to find a list of all the posts on my site. I used the `xargs` command with `wc` to calculate the word count of each post.

The `xargs` command is new to me. I am using it to retrieve items from standard input from my last command. I started using it because I saw a code snippet on Stack Overflow that only seemed to work with the xargs command. I'll keep experimenting with it. After some tinkering, I arrived at this command:

```
find -f website/_posts/* | xargs wc -w
```

While writing this section, I realized I can improve my command. I can just use the `wc` command with a wildcard to retrieve a list of all my posts and their word counts. The revised command looks like this:

```
wc -w website/_posts/*
```

I like this command better. It is shorter and easier to understand. I can avoid using xargs. Both these commands show the same output. At the moment, I am only interested in one metric: the total word count. This word count appears at the bottom of the list of word counts.

## Parsing the Word Count

I used the `tail` command to retrieve the last line from the `wc` command. This let me see the total word count. I then used `awk` to print out the total number of words on my site and the average number of words per post. I was interested in the total word count. It's nice to know that I have written (excluding this post) 106682 words for this site.

The average word count was a test of my bash knowledge. I used an arithmetic operation that divides the total word count by the number of posts on my site. To calculate the number of posts on my site, I used a separate command. I used the `wc` command with the `-l` flag to see how many posts were on my site.

```
post_count=`ls website/_posts/* | wc -l`
```

This command is assigned to its own variable for clarity. I didn't want to add too many pipes into my original script. I pass the variable `post_count` into my awk statement so that I can perform the arithmetic. The final command came out like this:

```
wc -w website/_posts/* | tail -n 1 | awk -v total="$post_count" '{print "Total Words:", $1, "\nAverage Per Post:", (($1/total))}
```

This lets me see the total number of words on my site and the average number of words per post. On average, a post contains 904.085 words. I expected a number in this region. I do prefer to write longer posts. This project was all about looking for interesting insights. I do not have any plans with the data. I just wanted to see if I could learn more about my word counts.

## The Ease of Bash

Bash is a versatile programming environment. It is bare bones. I thought about writing a static site generator in bash. I'm sure I could do it. The generator would be much faster than Jekyll. I would have to sacrifice features like live reload in development mode which I like. I decided a bash static site generator would be a step too far.

Bash is not ideal for everything. I learned about an external command that lets me parse JSON. I learned that I prefer to work in Python to parse JSON data. Bash may be capable of doing a lot but it doesn't mean I need to write every script in bash. I'm excited by bash. I do not want to go overboard.

I like to use the best tools for the job. I find that bash is good for programs where I need to work with the system. My analytics script read from a system file. This word count script works with the file system. I've been able to come up with solutions that are much more elegant than I could write in Python.

My word count script is two lines of code. I could probably move it into one with some trickery but I want my code to be readable. A friend advised me against taking too many shortcuts while writing bash code. I like this advice. I don't want my bash code to be so "clean" that it is unreadable. In Python, my word count script would have been dozens of lines of code. I would have had to use arrays and open files. It would have been a verbose script.

I do plan on learning more about bash. My itches have been scratched for the moment. I'm reading more about the UNIX philosophy. I do not have much to share because I am still learning. I am proud that I use macOS, a UNIX-based development environment. UNIX has been thought out so well based on my intital impressions of the philosophy behind the operating system.