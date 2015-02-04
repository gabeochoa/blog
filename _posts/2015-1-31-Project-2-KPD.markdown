---
published: true
title: Project 2: KPD
layout: post
author: Gabe
tags:
---


KPD is a project that I have been working on since december. It is an image downloader for Reddit written in Python. For now it is only runnable from the command line and supports imgur, imgur albums and gfycat webms. [github](https://github.com/gabeochoa/KPD/)

It also has config file support allowing you to specify your own subreddits and keywords to download in this format:
	subreddit :: name, name2, name3 
	subreddit :: * 
where subreddit is replaced by your own favorite subreddits (ie. Pics) and name... are replaced by the keywords you would like to download. (You can also use * to download all images from that subreddit)

It only searches the title name so if someones dog is called kitty or a person is mistaken on what city the picture was taken in, you might end up with pictures you don't want. Right now there is no way for the program to know what you want (might be possible to do with deep learning algo, feel free to fork the project :) ).

The images are saved in this format:
	subreddit/keyword/postname.extention or
	subreddit/keyword/postname/filename.extention (for albums)

The project was originally concieved as a way to not have to continuously check /r/kpics for new pictures of my favorite idols and I decided to make sure it worked with other subreddits as well. The name of the project is an acronym for **K****P**ics **D**ownloader.

The code is pretty simple python and used the praw api for reddit, imgurs python api and gfycats json api. In order to run this project on your own, you will need to acquire an imgur key and secret and place them in the keys.py file. 