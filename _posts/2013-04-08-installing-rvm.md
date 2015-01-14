---
layout: post
title: "Ruby: Installing RVM on Lion"
category: blog
published: true
---

[RVM](https://rvm.io/rvm/) is a version manager for the Ruby programming language, letting you install, run, and default to different versions of the language on the same computer. Ruby 1.8.7 is built-in on OSX Lion and I'm running a few programs that depend on it, but 1.8.7 is several years old and about to be deprecated -- if I want to learn some Ruby, I should probably use a more recent version like 2.0.0. 

So that's where RVM comes in. Since I'm a slightly doofus-y beginner and installations can differ according to terminal shell configurations, setting it up took some muddling through. These are breadcrumbs for me rather than instructions for anyone else; if you're trying to get started with RVM, you should use the official [installation guide](https://rvm.io/rvm/install/). But if you're on Lion and getting the error <code>rvm: command not found</code> after install, you might try step two below.

In terminal, install the latest stable release:

	\curl -L https://get.rvm.io | bash -s stable

You may or may not have a <code>.bash_profile</code> in your root directory. Since the filename starts with a dot, it's invisible by default; you can view hidden files in a given directory with

	ls -a

If you have a <code>.bash_profile</code>, you'll need to update it so your shell can find RVM:

	echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile

In theory, you've got RVM powers now. I started to install Ruby 2.0.0

	rvm install 2.0.0

but got an error -- RVM needed lots of missing packages to complete the install. I had to enable <code>autolib</code> so RVM could take care of those:

	rvm autolibs enable

Ran the install prompt again and that did it. Hurrah!