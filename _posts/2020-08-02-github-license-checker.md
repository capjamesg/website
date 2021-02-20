---
layout: post
categories: ["Coding", "Post"]
title: "GitHub License Checker"
---

I've been working on a few little scripts that scratch my itches. These scripts are not necessarily big enough to be their own Git repositories. I created one for my recent [XXIIVV webring searcher](https://github.com/jamesgoca/xxiivv-random) command line interface. The script itself was only a few lines of code. I do not think I need a full repository for it. Nonetheless, I made one.

A few moments ago, I wondered how many GitHub repositories I have that do not have licenses. This is important to me because I want other people to use my code that I put on GitHub and sourcehut. There shouldn't be a doubt in anyone's mind that they can use most of my projects.

That's why I decided to create a simple script that checks whether my repositories have a license and tells me if they do not.

I did not want to create a GitHub Gist to share this script. I feel like that would make me too dependent on GitHub. I believe sourcehut has an alternative but I'm not in the mood to explore a new platform. I'll just use this blog.

For those who are interested, you can view the script I used to check for licenses below:

```
import requests
import json

repos = requests.get("https://api.github.com/users/YOUR_USERNAME/repos")

final_repos = repos.json()

# Check for licenses

for r in final_repos:
	if r["license"] == None:
		print("{} does not have a LICENSE.md file.".format(r["full_name"]))
```

You should replace `YOUR_USERNAME` with your GitHub username. You do not need to be authenticated to use this script unless you want to search through private repositories. [Read more on the GitHub documentation website](https://developer.github.com/v3/repos/). I used a slightly outdated version of their documentation but it still works. Take note of this if you plan to build upon this script.