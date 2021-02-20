---
layout: post
categories: ["Technology", "Post"]
title: "Setting Up My Raspberry Pi"
---

I want to talk about a project I undertook yesterday. I set up my Raspberry Pi with a new SD card. I do not presently have the energy to think of a more interesting topic. These last few days have been tough. It happens sometimes. We all have days when we are not quite ourselves. This is a blog, not my journal, so I don't want to get bogged down in the details of reality. Here, I write about technology and coffee. To the story!

My weather station was built using the technologies I had available to me at the time. This was a Raspberry Pi, a Sense HAT, and, notably, an 8 GB SD card. I threw away my old SD cards when I was doing a cleanup of my room. I didn't think I would need them and at the time I was going for a minimalist vibe. I had one SD card left which is the one I used to set up my Pi.

With 8 GB, I could do a lot. While the Raspberry Pi operating system would take up a big chunk of the space on the disk, there would be plenty to play around with. I realized that this was not the case. When I started to install libraries for my weather station, I noticed the space on my Raspberry Pi quickly recede. Once I had configured the weather station, over 97% of my disk had been used.

## Replacing the SD Card

Realizing that I could not keep this up, I decided to purchase a new SD card. I got a 64 GB SD card for nine pounds. Not a bad deal. It was half-price. I was elated because SD cards can get expensive, especially for larger sizes. As I have come to expect from Amazon, delivery was swift. I am a Prime customer so the SD card arrived the next day.

I had prepared in my mind what I was going to do to make the transition from my old to my new SD card. I knew that there had to be a way to copy the contents of my old SD card to my new one. I found so many people on the Raspberry Pi forums and on Stack Overflow who shared the exact predicament that I was in. I was happy to see so much documentation around the issue. I found a command that let me create a `.img` file from my existing SD card. I could image this file onto my new SD card. Problem solved.

Well, it was not that easy. I used the Raspberry Pi Imager tool to image the `.img` file to my new SD card. I changed the SD card on my Pi. I booted my Pi and it did not load. I had to connect my Pi to my monitor to see what was going on. The Pi did not boot. Only a single underscore flashed on the screen. I didn't even see the four Raspberry Pi logos after I rebooted. This was not what I expected.

I imaged the SD card again. I hoped that I had just made a mistake the first time and that the second time everything would work out. This time, I had my monitor plugged in from the first boot. This would let me see whether I had accidentally corrupted my SD card the first time around by unplugging it too soon. I noticed the same behavior as the first time. My transition was unsuccessful.

## Setting Up the Operating System

I could have spent longer debugging. I did some searching to see what was wrong. I believe the issue I was experiencing could have had something to do with the different partition sizes. I explored a few solutions but none of them stuck. I gave up and decided to just start from scratch. I did not mind doing this because I had few plans yesterday and I needed something to occupy my time. What better way to use a day than to play around with a Pi?

I imaged a brand new version of Raspberry Pi OS to my SD card and began. I noticed that it took significantly longer to image Raspberry Pi OS to my SD card than it did to image my `.img` file from my old drive. This made me think that I had made a mistake when I created the `.img` file. It was too late. I had already imaged the new SD card.

I had to connect my Pi to the monitor because I needed to set it up with networking. I forgot that the Pi comes with a graphical user interface for setup. This was not a problem. It was a tad inconvenient having to plug my Pi into a keyboard, a mouse, and a monitor. I usually run my Pi headless. Nevertheless, I done what I had to do. I set my Pi up with my monitor and followed the setup instructions.

It took a while to install the updates for the system. During that time, I downloaded my Git repository and made sure I was ready to deploy my new weather station. I pulled up the documentation for Nginx so I could set up my new web server as quickly as possible. My Pi was live. After waiting a bit for the updates to install, I could reboot and get to work. It only took twenty minutes or maybe even less time to set up the new web server. I was done.

This was not how I expected to spend a Saturday but it did keep me occupied. When I don't feel good, I like to have a project to work on. Today's project was going to be an experiment with pixel art but I do not have the energy to read about Numpy arrays. Maybe another day. I've spent most of today reading about coffee. Not a bad way to spend a day!