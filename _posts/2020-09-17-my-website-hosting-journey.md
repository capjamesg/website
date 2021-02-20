---
layout: post
categories: ["Web", "Post"]
title: "My Website Hosting Journey"
---

My website has been hosted on a number of platforms over the years. Last year was my year of using CMS tools to publish my website. I used WordPress initially because it was easy for me to set up. I wanted a website over which I had more control and WordPress looked like a good option. At the time, I was not as comfortable with web development as I am now. I could build a website but I didn't feel ready to create my blog from scratch.

I moved to Squarespace because of their designs. I love their templates. I knew a few other writers who used Squarespace and their sites looked aesthetically pleasing. As a writer, I wanted my content to be front and center on my website. Squarespace let me do that more efficiently than WordPress, in my opinion. [^1]

These platforms worked for their purposes but I felt like both of them had significant deficiencies. Squarespace was pricey and my site was quite templated. I could create my own Squarespace template but I never found the time to delve deep into their documentation. Perhaps this was a blessing. My site would be developed into their templating system. This would make it harder to move.

## Building a Site

This year I decided to make my own personal website. I consider my website as my main side project. Someone at last night's HWC meeting said that they felt somewhat guilty to admit their personal website was their side project. I feel this way too. It doesn't seem like a blog is a project in itself when I see other people work on "portfolio projects." My blog brings me joy. I'm going to keep tinkering away with it.

I cannot use a tool like Squarespace if I want my own site. I had to build one myself, from scratch. The first version of my site was a Next.js website. The website was built in Next.js because I'd seen a lot of blogs use Next.js and it seemed powerful. I was right. The documentation was very intuitive. I think (although do not quote me on this) that their documentation gave an example of how to create a blog at the time.

I was happy working with Next.js because I had experience using JavaScript and React.js. I knew now was the time to finally build something of my own. Seeing people share information like quantified self data on their website gave me more conviction that I was on the right path. I wanted a site that I could share with other people.

## The Hosting

With a website in my hand, there was one question left to be answered: where should I host it?

I've tried a lot of hosting platforms. If you are ever weighing the pros and cons of a particular platform, let me know. I'd be happy to help. I first hosted my site on Heroku. I've hosted a lot of applications on Heroku before. It is really easy to use. Heroku worked well with Git. When I pushed a commit to my blog repository, Heroku got to work building the site. I was happy with this workflow for a while.

I then decided to move to Vercel. Vercel, formely Zeit Now, is the hosting service that accompanies Next.js. I wanted to streamline my deployment and Vercel fit my criteria. I could deploy from the command line. Like Heroku, I found Vercel easier to use. Because the platform was focused on the command line, I felt more in control. Vercel does have a nice user interface but I seldom needed to use it.

When I moved to a static website, I changed what technologies I used. Initially, I hosted my site on DigitalOcean. DigitalOcean has been reliable and I've never had a negative experience with their platform. For $5 per month, I can host my website. It's an incredible bargain. What I love about DigitalOcean is that I have a whole server to play around with, not just a deployment environment.

Last week, I felt an itch to change. DigitalOcean works but deploying my website took time. I had to set up an FTP connection every time I wanted to make a change. I know how to use FTP to transfer files but I'd rather not use it. I turned to Netlify. Netlify's main selling point was what Heroku and Vercel gave me for my dynamic applications: a good deployment workflow. Whenever I pushed a commit to my blog's GitHub repository, Netlify would get to work and deploy my site. Their services are powerful. Often, it only took a second or two to build my cached Jekyll site (not including setup time).

## Choosing an Architecture

I am still exploring my options for hosting. I've tried so many options. I feel good about shopping around because hosting is a crucial part of my workflow. I'm not the biggest sysadmin in the world. I can set up a web server and configure apache2 or nginx. When it comes to building more complex setups, I do not feel confident. FTP was just a bit outside of my comfort zone. I know it's simple but there are more developer-friendly options.

I change my website a lot. That's something that you should expect coming to this site. Infrastructure is not visible but to me it really matters. Heroku, to my knowledge, does not work with Jekyll. Vercel is a bit more than I need. DigitalOcean gives me a server to use, but I have to upload content over FTP. Every option has its drawbacks and advantages. Exploration is the only way I figure out what works when it comes to tech.

[^1]: I never delved too deep into WordPress. I got confused at many points and I found their software to be more powerful than I needed. I do believe that WordPress is a great tool for beginners to the IndieWeb, or for anyone else who wants to host their own site. You don't need to build your site from scratch. Just having a website is a great first step.

