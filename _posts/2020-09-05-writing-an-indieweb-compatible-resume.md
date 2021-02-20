---
layout: post
categories: ["IndieWeb", "Post"]
title: "Writing an IndieWeb-Compatible Resume"
indienews: true
---

I used to rely on services like LinkedIn and AngelList as a resume. I quickly gave up on them because I did not use those platforms much and it was a burden for me to have to change my information on so many silos. That's the thing about silos: you've got to learn their way of doing things. I never felt attached to my profiles on those sites.

This website has become almost my resume. I share my thoughts about the world on my blog. I build projects like my quantified self tracker. Until recently, I did not have an official resume. I could always share my GitHub profile and my website but I do not have anywhere that I talk about my professional history, also known as the serious side of me. That's why I decided that I was going to write a resume on this site.

## The First Version

The goal of this project was to share my professional experience. The easiest way for me to do this was to create a new page on my site that listed where I have worked and my education background. This was a good version one. The information that I wanted to share was freely available on my site. If visitors wanted to learn about my education history, I had a resume.

Earlier this week, I realized that there are ways I could improve my resume. The first issue that I had was that most people do not consider a web page to be a resume. They expect a PDF. I could ask someone to print off my resume but a web page never looks as good on paper as it does on the web. I also started to read about a microformat called h-resume that people were using to mark up their resumes. I wanted to join in.

## Making Improvements

I spent some time earlier this week reading over the h-resume markup specification. h-resume is a draft specification but I hope it becomes an official microformat.

In my [h-resume](https://microformats.org/wiki/h-resume) class, I included a h-card with information about my background and how to contact me. This is somewhat similar to the h-card that appears on the homepage of my website.

I have a separate h-card on this page because I want the marked up information available both on my resume and my homepage. It's not ideal because I will have to change both h-cards if a change is needed but it is the best I can do right now.

Within the h-resume class, there are three p-tags:

- p-experience
- p-education
- p-skill

The p-experience and p-education tags are also marked up as h-events. In those tags, I enclose my job title (or academic status), the time during which I was engaged in a particular activity, and a brief summary of that activity. I used these microformat tags so that my resume made the best use of microformats.

Here is the markup for one of my jobs:

```
<div class="p-experience h-event">
	<div class="h-card">
		<h3><span class="p-job-title">Technical Content Manager</span>, <span class="p-name p-org">Career Karma</span> - <time class="dt-start" datetime="2019-07-29">July 2019</time> - Present</h3>
	</div>
	<p class="p-summary p-description">Led <a class="u-url" href="https://careerkarma.com">Career Karma's</a> technical writing initiative. Wrote dozens of articles on HTML, CSS, JavaScript, Python, Java, and Linux, accompanied by code snippets and examples that explain each topic. Also assisted in product management on various initiatives.</p>
</div>
```

The professional and educational experience listings all include h-cards. These h-cards are used to outline my affiliation with a particular organization. In the above case, `p-name` corresponds with the organization for whom I worked and `u-url` connects to the URL of that employer. 

I am somewhat curious about why there is no `p-skill` parent tag. All of my skills are marked up as `<li>` elements in a `<ul>`. Each `<li>` element has a `p-skill` tag. There is no parent. It does not affect the function of the site. It's just something that I think is interesting.

## Print Styles

I decided to make my resume printable. The inspiration for this idea comes from [Peter Molnar](https://petermolnar.net/cv.html), whose resume is printable. His site also has a QR code that lets you download a v-card of his information. An interesting idea indeed. I have experimented with print styles on this blog before but the idea did not stick. I felt like the use case of printing out my site was so narrow that it was not worth including the print styles in the style sheet.

Adding in a print style has a real use case for the resume page. Often, people need a paper version of a resume. If I were to apply for a job, I could not link my blog as my resume in most cases. I'd have to send over a PDF or another document. Because I have formatted my resume using print styles, I can easily print out a version of my website.

The print styles remove the header, footer, and accessibility messages from the site. The styles also change the color of the headings on the page. The width of the page is changed to make sure that the page can be conveniently printed out on paper. The print style sheet is small but that's ideal. I do not want a bloated style page with print styles.

To preserve bandwidth, I only render this style sheet on the resume page. This means that you do not have to download the style sheet on all the pages which have not been specifically optimized for print styles. I accomplished this by using an `if` tag in my Jekyll `default.html` page. This tag ensures that the `<link>` association to my print style sheet is only displayed on the resume page.

*There are a number of excellent examples of IndieWeb resumes on the [IndieWeb wiki](https://indieweb.org/resume).*

## Another IndieWeb Project

I am starting to run out of ideas as to what I want to do with this blog. For the most part, my itches have been scratched. There are a couple of big itches, like storing my quantified self data, that I do not quite have the energy to address just yet. This project was exciting because I got to play around with microformats in more depth. Before working on this resume, I'd only experimented with a h-card and a h-entry.

I do like the idea of adding microformats to more of my content. Microformats make no difference to the end user but they do make my code both easier to read and more meaningful. I can't think of any services that explicitly use the h-resume format yet but I know that because a format has been defined then it is possible that someone could make a service that works with it. For instance, [IndieWeb News](https://news.indieweb.org/) supports submissions with pages that are marked up using h-entry and a syndication tag.

