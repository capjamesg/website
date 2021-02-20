---
layout: post
categories: ["Coding", "Post"]
title: "Learnings on UNIX"
---

I'm committed to writing posts about what I'm learning on the command line. I would like to take this commitment a little wider and explore what I am learning about Unix. I've come to realize that the command line is about more than just commands. It is about the Unix philosophy and how it makes applications what they are on the command line.

The Unix philosophy, the way I understand it, follows the principle of KISS. Keep it simple, stupid. Commands should do one thing and they should do that thing really well. That's because commands can connect with other parts of the operating system. The better a command is at doing one thing, the more likely it is that it's extensible. `cat` is a great example of an extensible command. It does one thing really well: it prints the contents of files to stdout. When I think about it, I've seen `cat` used in so many different ways alongside dozens of commands. It's so versatile.

## Files and Processes

Everything on a Unix computer is either a file or a process. Files are identified using codes called iNodes. Interestingly, these nodes are what make mv operations quicker than cp operations. All a computer does is moves an iNode elswhere when I run mv. Unix computers use a tree structure to store data. The name iNode probably comes from this tree: every item in the tree is its own node.

Processes are given their own identifiers. They are called `pids`, or process IDs. Every process has three files to which it can write: standard input, standard output, and standard error. The error output is for processing errors. Standard input is what I enter into a process or what other data is parsed into a process through a technique like redirection. Standard output is what a process returns.

The standard input and standard output are the same on a terminal. The same goes with standard error. That's why everything I type in a terminal comes with its own response. I never thought about it this way. It's also why I can write to different terminal windows that are in the `/dev/` directory. I can pass the standard output from one command into the standard input of a file in the `/dev/` directory. Amazing.

## The Process Lifecycle

Every process has three stages: fork(), exec(), and wait().

A new process is created by duplicating its parent process. Then, the process executes the command that it wants to run. When I run `cp` in my terminal, a duplicate of the bash process is created. That duplicate runs the `cp` command. Processes cannot share information with each other. What happens in one process stays in one process. The only information that a process can return is an exit code.

That's where the wait() stage comes in. Once a process is created, the parent process will wait for an exit code. That code will tell the parent process that a child process has either executed successfully or unsuccessfully. 0 denotes success. Every other number means there has been an error.

Every process starts off with a parent. That's because processes need to be forked. Processes do not need to have a parent to work. A process can become an orphaned process which means that it is not owned by a parent process. I'm not sure what happens when an exit code is returned by the orphan process. I'll need to look into it.

## Command Learnings

It's been interesting to learn more about the less command. Today I learned that less can be used to search through a file. I can run `/search_term` to find a term inside a less prompt. That means that less is a lot more powerful than I thought. It feels a bit more intuitive than using `nano` to find something in a file when I have no need to edit the file.

I also learned that I do not need to use the -n flag to work with the `head` and `tail` commands. I can just use a hyphen followed by the number of lines taht I want to access from a file. This speaks to the core of Linux: tools should do one thing really well. Head and tail do not try to be anything else. They're definitely not `less`. They just print the start or the end of a file. Really well.

I'm still exploring Unix. I am starting to feel a bit tired with all this new information coming in so I may take a break for a few days. I'll be back here tomorrow with something to say about something.