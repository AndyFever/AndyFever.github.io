---
layout: post
title: "Analysing Network Data for Performance Testing"
categories: blog
excerpt: "A quick blog that shows how to quickly analyse network data on a mac for Performance Testing"
tags: [cucumber, BDD, ruby, capybara, selenium]
date: 2017-08-17
---

## Analysing Local Network Traffic with Nettop

There are times when you're testing or developing that you need to see what is going on with your network connections. Admittedly that isn't very often, especially when you're testing. For those of use with the memory of a fish, this post shows a simple way you can do it on a Mac. It's built into Terminal and it's called Nettop.

#### Basic Nettop output

To get the raw output from nettop is pretty easy, just type:

    nettop

That's it, you'll get a pretty long list of connections with the relevant ports.  To make it easier to read just type 'p'. That will give you a friendlier output.

#### Formatted Nettop Output for Specific Interfaces

To see a cleaner representation of what's going on, you can use route.

    nettop -m route en0

This will give you connections over your wireless port. To see what's going on for a specific protocol, just use:

    nettop -m tcp

![Network information output]({{ site.url }}/img/nettop_output.jpg)

#### Viewing Network Traffic for Performance Testing

When you are doing some form of Performance Testing you need a more detailed and configurable output. This is where Wireshark comes in.  Wireshark is a very powerful tool and while it does have a bit of a learning curve associated with it, it’s well worth learning how to use it.

You can download it for Windows, Mac and Unix from [here]( https://www.wireshark.org/download.html)
