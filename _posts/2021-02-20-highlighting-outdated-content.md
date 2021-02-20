---
layout: post
categories: ["Web", "Post"]
title: "Highlighting Outdated Content"
---

I have decided to port over the posts from my previous blog onto this one as I believe there are a few insights to be gleaned from those past posts. But I faced a problem: the content is somewhat outdated in terms of its reference to my website, as I have completely redesigned my website.

To solve this problem, I decided to add a disclaimer to all of my old blog posts which allows me to inform my readers that the content they are reading may no longer be up-to-date.

I wanted to apply this disclaimer to all posts written before the start of this year (those which were from my old blog). I did not want to selectively apply a tag to each post because most of my older content makes reference to my old site and design philosophies.

To apply such a tag, I employed the use of Jekyll. I first assigned a variable which retrieves the date on which a post was published in the format "'%Y%m%d". I then added an if statement to compare this value to "20210101". This value represents the first day of the year.

If the result of my variable is less than the stated value, it means a post was published before 2021. So, I mark that post as outdated on my blog. Here is the full code that makes this feature work:

{% comment %} 
```
{% if nowtime < "20210101" %}
	<p>Published on {{ page.date | date_to_string }}.</p>
	<p class="outdated">This post is from the previous iteration of this blog and may be outdated.</p>
{% else %}
	<p>Published on {{ page.date | date_to_string }}.</p>
{% endif %}
```
{% endcomment %} 

Every post that meets the aforementioned rule displays the text "This post is from the previous iteration of this blog and may be outdated." below the date on which the post was published. I apply a dark red colour to this text to attract attention to the disclaimer.

Because I have dozens of posts on this blog, going through each one and adding a tag regarding the fact the post may have been outdated would have taken a while. Although some of my old content may still be relevant, as I often change my mind about technology I think this tag serves as a good reminder to view some of my more up-to-date content.