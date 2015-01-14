---
layout: post
title: "Responsive YouTube"
category: blog
---
YouTube embeds don't always play super-well with responsive layouts. This [StackExchange thread](http://stackoverflow.com/questions/15844500/shrink-a-youtube-video-to-responsive-width) has a nice solution. In the stylesheet:  

	.videowrapper {
    	float: none;
    	clear: both;
    	width: 100%;
    	position: relative;
    	padding-bottom: 56.25%;
    	padding-top: 25px;
    	height: 0;
	}

	.videowrapper iframe {
    	position: absolute;
    	top: 0;
    	left: 0;
    	width: 100%;
    	height: 100%;
	}

And within a responsive element on the page:  

	<div class="videowrapper">
	  <iframe src="funvideo"></iframe>
	</div>

And now you can spend five minutes resizing your window over and over, if you're anything like me.