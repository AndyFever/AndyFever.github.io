---
layout: post
title: Jekyll and no hide
excerpt: "Why the world needs yet another technical blog hosted statically through github and generated with Jekyll"
modified: 2017-08-17
categories: articles
tags: [jekyll]
image:
  feature:
  credit:
  creditlink:
comments: true
share: true
---

I've been looking at setting a blog for quick and easy posts for a while now. As ever, I wanted to get
my hands dirty with some coding rather than using some out of the box option where I have no control.

<figure>
	<a href="https://jekyllrb.com/img/logo-2x.png"><img src="https://jekyllrb.com/img/logo-2x.png" alt="image"></a>
</figure>

Rails seemed to be the perfect fit for the task, autogenerating the framework I needed allowing me to
focus on styling and hosting. Unfortunately after going to Rails 5 I spent far to long getting active record to work, meaning I was digging around version numbers embedded in the code. So it was time to move on to something faster.

Up steps Jekyll which is static framework that allows you to create blogs using markdown (awesome!) and
host it through GitHub (even better!!)  It has no DB, so I needed to do some digging around various gems and themes as I definitely need
features like tags.

#### Update
<p></p>

So I tried a few themes but the tagging proved a bit painful (it's been a while since I've used a computer in anger). So there was a slight struggle until I found this basic framework setup (linked to a blog from [So Simple Theme](https://github.com/mmistakes/so-simple-theme)). Over the next few days I'll
extend it using things like Coffee and Sass.

I just need to extend the framework so other people can contribute (you never know, they *might* want to)
