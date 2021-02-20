---
layout: post
categories: ["Coding", "Post"]
title: "Mirroring my Code to sourcehut"
---

I finally got around to mirroring my code to [sourcehut](https://sourcehut.org/). I had the idea about a week ago. I tired quickly of it, but I could not get the idea of creating a copy of my code out of my head. This morning I decided to finally get around to doing it.

## Losing Faith in GitHub

GitHub, as I often forget, is owned by Microsoft. Since the acquisition, GitHub has changed so much. I read that they are [experimenting with READMEs for user profiles](https://www.aboutmonica.com/blog/how-to-create-a-github-profile-readme). I feel like a lot of the changes GitHub has made recently are unnecessary for my needs. I like the idea of dependency tracking but I don't like getting emails about my old projects asking me to update my dependencies. I do not use actions or many of the new features. They even updated the UI recently. I'm not sure if I prefer it to the old one.

It's not that GitHub is not useful. I feel like having a GitHub profile is an almost necessary part of being a developer. That's the problem: it is trendy to have a GitHub profile. The purpose of code hosting platforms is not to be part of a trend. It's to host your code.

GitHub is presently building features that I myself do not need in my day-to-day programming. I can refuse to use them but I'd rather that they were not there in the first place. For some developers, I'll bet GitHub's recent changes are a net benefit. That is not the case for me. Between dependency tracking, security notifications about old repositories, and UI changes, I believe it is time for a change.

## The sourcehut Solution

I learned about sourcehut a few weeks ago. They are an open-source platform for code hosting. Sourcehut does more, like offering Mercurial hosting, but I've only explored their Git hosting solution. I came across them when I was doing research about alternatives to GitHub. It turns out that there are a lot of good platforms. Gitea is one of them.

I decided that sourcehut was for me for a couple of reasons. Sourcehut has a really good UI. It's more text-based than GitHub and it does not have a lot of the bells-and-whistles present on GitHub. It's bare-bones and that's what I like about it. I don't spend a lot of time using the GitHub user interface because I do most of my code edits on my local machine. I don't need to interact with a user interface often. When I do, I'd much rather work with a simple one. Sourcehut looks like a good solution.

Sourcehut is open source software. This excites me for the same reason that I have started to use more open source software, like KeePassXC: it is powered by a community of passionate developers. Unlike GitHub, whose code is owned by Microsoft, sourcehut is owned by its contributors. This is great because I know that there will be passionate debates behind every feature. These debates probably happen at GitHub. The difference is that sourcehut doesn't have an incentive to make a profit: they are building for the good of the developer community.

I discovered that sourcehut has a good API. I will probably not use it often. I only know it has a good API because, as I will talk about in a minute, I wrote a script to automatically upload my projects to sourcehut. Having this API available makes me feel comforted in some way. I know that I'll be able to extend the platform if I need to. GitHub has a good API too. The API is not a dealbreaker either way.

I believe I can host my own instance of sourcehut. I am presently hosting my code on their public instance because it was easier for me. The purpose of having this mirror is to have a backup of my code. I'm going to research how I can create a local backup of my code. It may be the case that I create a Git repository on my Raspberry Pi to which I back up. I'll need a bigger SD card!

## The Migration

What put me off migrating sooner was that mirroring my code looked difficult. I wasn't sure what to do. I found a good resource on the GitHub documentation that helped me figure out how to do it.

The next barrier I faced was time: it would take so long to migrate all my repositories. I spent an hour or two this morning creating a script which  uploads my code to sourcehut. The script creates a repository if one does not exist and creates a mirror of the GitHub version of that repository. Mirrors are only created for repositories over which I am the owner. Forks and projects associated with an organization, like my work tutorials, are not cloned.

I have made this script [publicly available on GitHub](https://github.com/jamesgoca/sourcehut-uploader). I will make it available on sourcehut when I iron out a few kinks that are in the project. I'd like to make it as intuitive as possible so that anyone can easily migrate over to sourcehut. I will warn you that the script is slow. It clones all your repositories from GitHub, creates a mirror, and uploads them to Sourcehut. I have added in some logging so that it's easy for me to track what is going on in my code.

This is an attempt for me to take back control over my code. I was introduced to GitHub when I first started. Since then, it has become the de facto standard for hosting my code. Until recently, I had never thought about alternatives. Knowing that GitHub is owned by Microsoft made me think twice. I will still use GitHub as my main code hosting source. It's a great platform. I will use Sourcehut as a backup and create a new mirror of my repositories every month. There's a whole world of Git outside of GitHub. I'm only just starting to explore it.