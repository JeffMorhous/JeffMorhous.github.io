---
layout: post
title:  "Block Ads for Your Entire Home Network with a Raspberry Pi"
author: jeff
categories: [ Tutorial, Project ]
image: https://miro.medium.com/max/1400/0*TCrEJluo7rbs8Gh0
featured: false
hidden: false
---

I got a Raspberry Pi for my birthday last year and have been _suffering analysis paralysis_, trying to figure out what I want to do with it.

I recently came across some  [open source software called Pi-hole](https://pi-hole.net/), that boasts the ability to block ads for your entire network. Perplexed, I had to see how this worked, so here’s how I set up my Raspberry Pi to act as a black hole for all things advertisement related. Not only will you experience a (mostly)  **ad-free internet**, but things like Smart-TV’s and other “sketchy” analytics tools won’t be able to send their data home.  **Hurray privacy!**

If you have any questions, leave a response below or feel free to  [tweet me!](http://twitter.com/jeffmorhous)

----------

# Step 1: Aquire Hardware 🖥

The Raspberry Pi is an incredibly cheap computer, which makes it a great candidate for such a specific task. I’ll put affiliate links to each of the items that I purchased below, for your convenience.

I have the  [**Raspberry Pi Model 3 Model B**](https://www.amazon.com/gp/product/B01LPLPBS8/ref=as_li_tl?ie=UTF8&tag=jeffmorhous-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B01LPLPBS8&linkId=f500311a42eb9157e8bb09d28fbbdb0d), which costs roughly $50. I actually bought  [a kit that has a power supply and case](https://www.amazon.com/gp/product/B07BC7BMHY/ref=as_li_tl?ie=UTF8&tag=jeffmorhous-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B07BC7BMHY&linkId=4ea6501768e21eee68c1c20cbe40108d), which you may want to do as well. It’s wireless, so I didn’t need an adapter. However, if you buy a model without WiFi, you will need to either wire it into your router with an ethernet cable or buy a WiFi adapter.

You’ll also need a  [**microSD card**](https://www.amazon.com/gp/product/B073JYVKNX/ref=as_li_tl?ie=UTF8&tag=jeffmorhous-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B073JYVKNX&linkId=df3f3cfdac52cbe11f25e46a1c32d62e)  to store the operating system (more on that later). If your computer doesn’t have an SD Card Reader, you’ll need an  [**SD card reader**](https://www.amazon.com/gp/product/B00W02VHM6/ref=as_li_tl?ie=UTF8&tag=jeffmorhous-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=B00W02VHM6&linkId=68cd82405719a6437a054f482d20e3ed).

If you don’t have it already, you’ll need a simple keyboard. I’m going to assume you have some kind of HDMI display available, like a relatively modern TV, but if you don’t you’ll need that too.  _(There is a way to set up a Pi without a keyboard, mouse, or even a screen. It’s called a headless setup, and if you do this, then you can go ahead and skip to step 4)_

# **Step 2: Install An Operating System 👨‍💻**

The Raspberry Pi is pretty bare-bones. You can choose your operating system, and I went with  **Raspbian**, an open source port of the Linux operating system.  [You can find the downloads here](https://www.raspberrypi.org/downloads/raspbian/)  — it’ll take a hot second, so go ahead and hit download and feel free to read ahead.

Put your microSD card in your computer directly or through whatever adapters necessary. An important note is that I’m on mac, so my instructions here will be as such.  [If you’re on Windows, here’s some more generic instructions.](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/3)

[Download balenaEtcher to help us install Raspbian on the SD card.](https://www.balena.io/etcher/)  Run the .dmg to install it and fire it up.

![balenaEtcher on my machine](https://miro.medium.com/max/3212/1*zckppIkSuGw56jJ-w1IOqg.png)



Click on the blue “select image,” and find the .iso file of Raspbian that you downloaded. Ensure that the center selection is set to your SD card, and hit FLASH! Again, this will probably take a minute ⏰

Finally, eject your SD card and put it in your Pi. Plug in your monitor/TV, keyboard, and mouse

# Step 3: Customize Some Pi Settings

The Pi will ask you for your country and timezone, and then to change the default password — which you’ll definitely want to do for security reasons. Next, your Pi will probably want to update. Again, for security, go ahead and let it do that.  _This is probably the longest wait._

## You’ll also want to enable SSH, so you can control the Pi remotely 😃

To do this, open up the terminal in your pie by clicking the icon in the top left corner. Run the following command to get access to ssh (all of these should be run in your pi’s terminal, not your main computer)

sudo apt get install ssh

Enable it with

sudo /etc/init.d/ssh start

Set it to enable ssh every time it boots up with

sudo update-rc.d ssh defaults

To get your Pi’s IP address, run

hostname -I

## Now we switch back over to your mac’s terminal, where you run the following

ssh pi@YOUR.PI.IP.ADDRESS

And BINGO, enter your password and you now have remote access to your Raspberry Pi.

Note: It’s also a good idea to change your default SSH port, but we won’t go over that here.

# Step 4: Install Pi-hole

Either in your Pi’s terminal or your computer’s terminal connected to the Pi via SSH, run the following command from Pi-hole’s website to install it:

curl -sSL https://install.pi-hole.net | bash

The installer will run and ask a bunch of questions. It’s okay to choose the defaults, but feel free to customize like I did.

When the installer finishes it’ll show you the password it selected. Note this and copy it, then change the web dashboard password by executing:

pihole -a -p

# Step 5: Configure Devices or Router

Now that your Pi-hole is acting as a DNS server, we need to make sure that your devices use it instead of your ISP. You can do this on a per-device basis, but I’d recommend changing it at your router. That way, every time a device on your network makes a DNS request, it will first go through the Pi-hole.

This step is very specific to the brand of router, so I won’t go into detail. Essentially you need to tell your router to treat your Pi-hole as a DNS server, rather than your ISP. You should also reserve a static IP address for your Pi to ensure it’s IP does not change because this would break your setup.

**And Voila, enjoy your ad-free internet! 🙌**

----------

# Optional: How Pi-hole Works 🎓

Normal Ad-Blockers allow advertisements to load and just hide them from your view. Once you’ve gotten the Pi-hole up and running, advertisements will stop dead in their tracks, before they even begin to download.

Pi-hole is a very specific  [DNS sinkhole](https://en.wikipedia.org/wiki/DNS_sinkhole). DNS stands for Domain Name System, and it is the protocol for connecting names (like medium.com) to IP addresses ([104.16.120.127](https://myip.ms/info/whois/104.16.120.127)), which is where websites/servers really live on the internet.

A DNS sinkhole acts in place of your usual DNS provider to provide false results. This pretty much breaks your internet — NEAT! With Pi-hole, everything that isn’t an Ad gets forwarded to your DNS provider,  _but_ if the domain name is in Pi-hole’s blacklist (which is customizable for the nerdiest among you), then the Pi-hole sends back a fake IP address.

So you visit a website and it loads. Next, the website asks its ad provider for ads, and Pi-hole says “What ad provider? That doesn’t exist.” And boom your ads are gone. This can actually speed up your network, as you won’t be using as much bandwidth.

An interesting note is that Pi-hole won’t kill youtube ads, as youtube serves its content and advertisements from the same DNS, so killing youtube ads would also kill youtube.

----------
<iframe src="https://iosbynight.substack.com/embed" width="100%" height="320" style="border:1px solid #EEE; background:white;" frameborder="0" scrolling="no"></iframe>