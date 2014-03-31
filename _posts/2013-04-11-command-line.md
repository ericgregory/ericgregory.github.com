---
layout: post
title: "Bash: Basics and miscellany"
category: code
published: true
---

Running notes and reminders on basic bash (and some other useful commands, in no particular order, that wouldn't really make sense in another post).  
  
<code>cd</code>: change directory  
<code>ls</code>: list contents of directory  
<code>pwd</code>: print working directory  
<code>hostname</code>: what's this computer's name?  
<code>mkdir</code>: make directory  
<code>rmdir</code>: remove directory  
<code>touch</code>: make empty file  
<code>cp</code>: copy file (<code>-r</code> for dir)  
<code>mv</code>: move or rename file  
<code>less</code>: view file (q to escape)  
<code>cat</code>: view file without stopping or paging  
<code>ctrl-c</code>: stop program  
<code>sudo !!</code>: run last command as root
  
<code>pbcopy <</code>: copy file contents to clipboard  
<code>open -a [application.app] [filename]</code>: open file with a given application on OSX  
<code>chsh -s /bin/bash</code>: change shell (in this case, to bash)  
<code>sips -Z 600 *.jpg</code>: batch resize, retaining aspect ratio, longest side will be 600px  
<code>dig +short txt [searchterm].wp.dg.cx</code>: ask Wikipedia for a text record and short URL via DNS