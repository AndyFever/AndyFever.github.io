---
layout: post
title: "Agile Testing with Cucumber"
modified:
categories: blog
excerpt:
tags: [cucumber, BDD]
date: 2017-08-17
---

One of the surprising things about getting QA teams started with automated testing using BDD is how flexible it can be. You can get started on a basic framework even if you have minimal user and developer support.

Of course it is better if other roles are involved at a frameworks inception but that shouldn't necessarily be a barrier to it happening at all.

### Choosing a Testing Tool

I have used various agile testing tools, but the best was Cucumber. It is important to remember that cucumber isn't a automated testing tool itself, it is a parsing tool for linking requirements written in a business domain language to the tools that implement the test. I'll write a blog somewhere else why this a good thing and we shouldn't just code automated tests directly.

<figure>
	<a href="https://cucumber.io/images/cucumber-logo.svg"><img src="https://cucumber.io/images/cucumber-logo.svg" alt="image"></a>
</figure>

Cucumber can be used with various other technologies including WATIR (a collection of Ruby libraries providing an API for working with browsers), Java, Ruby... The most successful implementation I have worked on was Cucumber with the implementation layer written in Ruby with Selenium (providing interaction with chrome and Firefox) and Capybara. Capybara help implements with BDD paradigm and speeds up greatly the coding process. It even allows people with less technical skills to write some of the more simple acceptance tests.

This sets up the context for what a few of the blog posts that follow. I'll cover how to implement this framework for a fictional website and how some of the aspects of BDD can work from my experience.

### Useful Links:

[Capybara GitHub repo](https://github.com/teamcapybara/capybara "Link for Capybara")

[Cucumber Homepage](https://cucumber.io/ "Link for Cucumber Tool")
