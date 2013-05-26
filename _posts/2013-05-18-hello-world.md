---
layout: post
title: "Hello World!"
description: "My first Jekyll post"
category: 
tags: []
thumbnail: /images/uploads/2013/05/screenshot-from-2013-05-18-214215.png
preview: "Hello World! My blog is moved from wordpress to here!"
---
{% include JB/setup %}
When I decided to host my website on github pages, it became a necessity to look for a good templating engine and static generator. First I tried [Funnel](http://www.github.com/shuhaowu/funnel) written by a colleague of mine. Funnel was nice and simple but it was some how limited to my needs. I checked out [Jekyll](https://github.com/mojombo/jekyll) and found it to be awesome. With some initial setup I managed to start customizing and coding the templates. Also, since I had an old blog on wordpress I needed to migrate my old posts. 

The migration was not as messy and was almost fully automated. First,I exported my posts from wordpress using the export tool. Then, I was about to write my own wordpress to Jekyll markdown importer, when I realized may be somebody has done it already. And ofcourse they have. Amongs the many others, I found [ExitWp](https://github.com/thomasf/exitwp) simple to use. After generating the markdown version of the posts, I had to do some cleaning. I then wrote my own template to have them nicely presented on my blog page. Everything worked out nice.