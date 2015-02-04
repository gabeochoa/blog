---
published: true
title: Project 1 Pokemon Reboot
layout: post
author: Gabe
<<<<<<< HEAD
tags:
=======
tags: 
>>>>>>> c2148a900209b80bb5ae78a9013cc1598f26c975
---

This project is a pygame (Python) project started by a friend Brett. His plan was to recreate the generation 3(?) games in pygame to learn about games programming and flex his python muscles. When I joined the project he had I believe about 6k lines of code.

Check it out on [github](https://github.com/B1anky/Pokemon-Game)

![image](https://31.media.tumblr.com/d7f384cf0638331fa0b1f3ef3c550302/tumblr_inline_nj0urrFyvy1r786p5.png)

(This is what I first saw when he booted it up)

For this project, the main thing I have worked on is the basic player movement and the screen camera. In the pokemon franchise the movement is one that is both real time and grid based. This poses a problem of allowing the player to continue moving fluidly while stopping on a grid when input is ceased.&nbsp;

<iframe width="500" height="281" id="youtube_iframe" src="https://www.youtube.com/embed/XyLFcIKnzLg?feature=oembed&amp;enablejsapi=1&amp;origin=https://safe.txmblr.com&amp;wmode=opaque" frameborder="0"></iframe>

(Here is a webm of what I implemented, still working on the scrolling camera)

For walking the way that we decided to do it was to use a target x and y. Here is an example of what the code looked like before being integrated into the engine. 
{% highlight python %}

#outside gameloop
TILEWIDTH = 32
TILESTEP = TILEWIDTH/4
target_x = player_x
target_y = player_y
player_moving = false

#inside gameloop

if target_x < player_x:
	target_x += TILESTEP
if target_x > player_x:
	target_x -= TILESTEP
if target_y < player_y:
	target_y += TILESTEP
if target_y > player_y:
	target_y -= TILESTEP

if target_x == player_x and target_y == player_y:
	player_moving = false

if event.type == pygame.KEYDOWN:
		if event.key == pygame.K_LEFT and !player_moving:
			target_x -= TILEWIDTH
			player_moving = true
		if event.key == pygame.K_RIGHT and !player_moving:
			target_x += TILEWIDTH
			player_moving = true
		if event.key == pygame.K_UP and !player_moving:
			target_y -= TILEWIDTH
			player_moving = true
		if event.key == pygame.K_DOWN and !player_moving:
			target_y += TILEWIDTH
			player_moving = true
{% endhighlight %}