---
layout: post
categories: ["Coding", "Post"]
title: "Adventures on the Command Line"
---

I am going to start documenting my adventures on the command line. I cannot promise that it will be as enticing as, say, an actual adventure. I can say that these posts will be a catalog of what I'm learning about.

I've decided to spend a bit more time learning about the command line. I remember when I was in high school there was a point when I wanted to be a system administrator. The command line really interested me. My Raspberry Pi was what I consider to be my first exposure to a real command line. I'd seen command prompt on Windows but that was nothing like the Linux command line.

## Abstraction

I read a blog post yesterday about [Graphical User Interfaces (GUIs)](http://mjt.sdf.org/writing/gui/index.html) and command lines. The author mentioned that it would be impossible for any piece of software to implement every possible feature that the command line has. That's because everything in the command line can be customized down to the letter. I can set exact file permissions using the same letters and numbers that my OS uses. Finder abstracts most of this away.

Abstraction is good for the average user. I wanted a Mac because it would allow me to do iOS development. I liked how it was not as technical as other operating systems. Macs abstracted away what I did not know. Now that I'm more familiar with computers and the Unix sturcture, I feel as though I am ready to delve deeper into the weeds.

What's really interesting about the command line is that every command is modular. That's why GUIs need to abstract. I can't imagine a piece of software that integrates all of the features the command line offers. I can run "less" with any command to paginate the output. I can run "cat" and use a redirection operator to move the response from a command (which I think is called stdout) into a file. It's amazing.

Part of the Unix philosophy, which I am only now learning about, is that commands should do one thing really well. They should specialize. That command can then depend on other commands to help it do other things. Each command does not need a pagination option. I can use commands like head and tail to paginate, accompanied by a piping operator.

## The Less Command

Enough with the philosophy, let's get down to an actual command. Yesterday I started playing around with the less command. I hear there is one called "more" as well. I'm not quite at the point where I am exploring that one. 

What I like about less is that it gives me complete control over how I view a file. I can specify the exact number of the line that I want to view. I can use the up and down arrows to scroll through a document. I can use the space bar to move up and down pages. It's an incredibly powerful tool.

I can combine the less command with another command to see its output. I used it with the "finger" command to see how many users were signed in to my Mac. It's not the best use. I only have my own user. It was nice to play around with redirection. I used less with a few files too and tried to navigate through them. I'm now a bit more confident using the command.

## Grep

I've known about grep for a while. I have never really tried to use it. The finding feature on Mac sucks. That's the only way I can describe it. It is slow and there are parts of me that think most of that slowness is down to some graphical magic that Apple needs to do (like making a file appear in a Finder window). I find that grep is so much faster and more customizable. I can search inside files.

I came across grep while trying out the Linux Command Line Challenge. I've hit a brick wall with this challenge for now because I'm still learning about the command line. I will go back to it when I feel a bit more confident. The challenge asked me to find a word in a folder recursively. I wrote the command `grep -r "whatever word it was" .` and lo and behold I was able to find the word in the files.

I am fascinated with how grep can help me. I can't think of many use cases just yet. I'll need to use it a bit more.

## My Next Adventure

I'm not sure what my next adventure will be. I am presently reading an [article on learning Unix](https://neilkakkar.com/unix.html) which has been informative. I learned that "move" operations are so quick because they just modify the file structure. The file's iNode still stays the same. The only thing that changes is where a file is entered on the file system. Copy actions, on the other hand, need to move data. That's why they take longer.

I learned that everything in Unix is either a process or a file. Processes have their own metadata. I learned that even directories are files. I tried to open up the `.` directory in vim (because it would not work in nano) and I saw a list of all the files in my current folder. Amazing! One interesting discovery I made yesterday was the `cal` command which shows a calendar in the terminal. It's a simple utility yet so fascinating.

I am enjoying my time learning about Unix. I feel like I have the right know that I need to start experimenting a bit more. I hope to write more about what I learn in coming days so that other people like me can potentially learn from what I am learning.