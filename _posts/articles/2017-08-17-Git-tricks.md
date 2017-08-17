---
layout: post
title: Git Hints and Tricks
excerpt: "Here are some simple shortcuts and commands I use when using git in Terminal"
modified: 2017-08-17
categories: articles
tags: [git]
image:
  feature:
  credit:
  creditlink:
comments: true
share: true
---

One thing that drives me insane is not using some of gits more useful tricks for a few days
and forgetting them. So to help my challenged neural plasticity I've bashed together this blog with a few hints and ticks.

This article will be updated as my knowledge improves.

### Adding and Committing in one go

This is pretty simple with git aliases coming to the rescue. First, set up the alias

    git config --global alias.add-commit '!git add -A && git commit'  

Then just reference it when you need to add and commit a file.

    git add-commit -m 'pithy message'  

### Aliasing

I am a very bad typer, it's an established fact. So the less typing of long words I have to do the better. This is where aliasing comes in. To substitute one command for a hopefully shorter one, just follow the instructions:

Firstly, update your .bashrc file with the command you want.

    alias gs='git status'

Then save the file. To force terminal to reload the file use the following command:

    . ~/.bashrc

You will now be able to use the command gs.

### Stashing code changes

This is one I have use a lot (and maybe overused), it takes all of your changes in the current branch and saves them, reverting the branch back to the head.  Running it is simple:

    git stash my-changes

Then your directory should be clean. If you want to revert the changes:

    git stash pop

If you have stashed a lot and want to clear the stash then use:

    git stash clear
