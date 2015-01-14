---
layout: post
title: "Python: pip and virtualenv"
category: blog
tags: 
---

<code>pip</code> is a package manager for Python modules; <code>virtualenv</code> turns a given directory tree into an isolated Python environment so you can use different module versions for different projects on the same machine. They really go hand-in-hand, and I realized pretty quickly that they're more or less mandatory if you're working on multiple projects in Python. [This guide](http://dabapps.com/blog/introduction-to-pip-and-virtualenv-python/) explains both modules and the setup process super well -- below is a quick-and-dirty reference for feeling out your Python environment and then getting up and running.

While not strictly necessary, I'd like to see which modules I have installed by default. So in terminal:

	pydoc modules

Okay, no <code>pip</code> (which is itself just a Python module). To install it, we can use the older, creakier, and not-particularly-recommended package manager, <code>easy_install</code>. This is fine for grabbing <code>pip</code>, but you don't really want to use it for anything else. (This may require sudo.)

	[sudo] easy_install pip

We *could* use this installation of pip to install modules globally (which may require sudo too) 

	[sudo] pip install [module]

but we're probably not looking to do that too often. Instead, just as we used the not-quite-recommended <code>easy_install</code> to grab a better tool, we're going to use this global <code>pip</code> to grab <code>virtualenv</code>:

	sudo pip install virtualenv
  
Now we can head to the directory where we want to work on our first project. I made a directory called <code>pyground</code> for fooling around, so I <code>cd</code> to that and enter

	virtualenv env 

This creates a new Python virtual environment inside the current directory, storing everything at <code>your_directory_name/env/</code>. Now (automatically packed in with your virtual environment!) you have a version of <code>pip</code> local to this environment, and this is what you'll want to use to install a module to your working directory. To use this version of <code>pip</code>:

	env/bin/pip install [module]

Note that you won't have to use sudo here, because you're not installing globally. You can check to see which modules you've installed via pip in this environment with

	env/bin/pip freeze

And to run virtualenv's local version of Python, you'll use  

	env/bin/python 

And that's it. You can repeat this process for as many environments as you like. The walkthrough linked above offers a way to cut down on typing and temporarily make your shell recognize a given environment's pips and pythons as the default, but I kind of prefer to type out the env/bins.
  