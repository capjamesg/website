---
layout: post
categories: ["Coding", "Post"]
title: "Documenting My Code"
---

A few days ago, I decided to build a command line interface for the Garfield web comic. I wrote about my experience building this command line last week. I used a library called Click to create the command line using Python. Initially, the command line interface was going to be powered by the Python shell. Click allowed me to take the project a step further and build something that would run natively as its own command.

One of the things that struck me was the quality of the Click documentation. It was so easy to read. As a developer, I cannot tell you how much I appreciate good documentation. The better a piece of documentation is, the more likely I am to stick with using the software it is documenting. I did some research into othehr methods of building a command line interface with Python but Click had the most resources.

I have decided to start documenting my own code a little better.

## GitHub Repositories

When I set up a repository on GitHub, I am asked if I want to create a license file, .gitignore file, and a README. I used to skip doing this because I usually work on a project locally first and then deploy it to GitHub. Pre-populating these files would probably result in a merge conflict that I would have to fix. I create READMEs and such myself.

For my last few projects, I have been making a conscious effort to add in these pieces of documentation. These are considered de facto standards in Git repositories but I haven't thought about how useful they can be until now.

A README.md file is my first imperssion of many of the tools with which I work. A project with a good README gets my attention; a project with a great README is one I am probably going to use in some way. The better a package is documented, the easier it is to get started working with it.

I hadn't thought about how people may see my code and think "how can I run this?" I decided that I needed to start writing more detailed ones. Now, when I work on project, I make sure that there are installation instructions and authorship information in a README. It is the least I can do for people who encounter my code.

I must admit that part of the reason I am doing this is for the sake of appearances. When people look at my code, I want them to feel like I have invested a lot of time in it. I like to deliberate over every line of code and consider whether it is useful. I like to think about alternative ways of doing something before committing to a path. Good documentation helps me show that I put care into every part of my project. It's not just the code that matters.

I would not use my Garfield command line interface if it had no installation instructions or reference guide. I would have to look through the code to understand how it works. That's why I wanted to be more careful about documentation. I wanted to create a repository that I myself would use.

## Comments

I'm somewhat tempted to write a blog post about all of the parts of programming that I have changed my mind over in the past. Commenting is certainly one of them. As a naive young software engineer, I used to focus on the code at all costs. Now I like to spend time writing deliberate comments. I don't do this so much on my web pages. I feel like they are often unnecessary. On second thoughts, comments could help me keep track of how I center components and align `<div>` tags. Those are two tasks that I always seem to get confused about.

At the weekend, I was working on an archiving project. I'm not sure if I will revisit it but I enjoyed building it. There are quite a few comments across the project that speak to the intent behind certain functions. It was one of the more complex Python programs I wrote. When I was writing my code, I was concerned that I may lose a sense of how it worked quickly. That wasn't going to be good for the long-term viability of my code. I wrote a few comments to keep track of what is going on and when in the program.

## Software Best Practices

I'm sure that there are lists of software best practices. I'm probably not in compliance with them all. I have learned to appreciate documentation more now that I am working on more personal projects. What really set this off in my mind was thinking about how employers may see my code. It's good to have examples but if they are not well documented then they're not going to be as effective.

I am committed to documenting my code. I built a small utility that initializes a Git repository with an MIT license, README.md, and a .gitignore file. This utility will ensure that when I set up a new repository on my computer I don't forget about these crucial parts of documentation. Licenses are especially important. I want other people to riff on my code. Having no licence doesn't promote this behavior; it hinders people exploring your work.

Documentation can sometimes be boring. That's fine. It's often not as glamorous as coding. I am starting to fall in love with the idea of a well-polished README.md with good documentation. I would like to have one on all of my best projects. It's a sign of care; a testament to my passion.