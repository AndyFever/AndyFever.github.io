---
layout: post
title: "Agile Testing with BDD"
modified:
categories: blog
excerpt:
tags: [bdd, cucumber, automated-testing]
published: false
image:
  feature:
date: 2017-08-22T08:08:50-04:00
---

BDD is a killer way to get a cross-functional team all contributing to the software. In this post I'll describe what it is and how I've set teams up to do it.

This post starts from the basics. So if you have some awareness of BDD then feel free to skip the first section.

#### What the hell is BDD?

Yes, it another one of those acronyms we love so much in Software Engineering. This one stands for Business Driven Development. This fancy title is a processes that helps to solve some of the structural problems in development i.e. describing the software we want in a way that's quick and everyone from Developers to end users can understand. Let's give you an example.

*Example Acceptance Criteria*

This describes in simple terms what a function is supposed to do from the users perspective. It is quick write, quick to review and easy to manage. Anyone with an understanding of what the business requirements are can produce them.

The beauty of writing requirements in this way is that we are essentially writing what we want to test. If the acceptance criteria doesn't work, the test has failed.  This is where BDD test tools step up to the plate. In cucumber we put these acceptance criteria into what is described  
