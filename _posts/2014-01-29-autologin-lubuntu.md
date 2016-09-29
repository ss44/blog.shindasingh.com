---
id: 1380
title: Autologin Lubuntu
date: 2014-01-29T01:54:21+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1380
permalink: /2014/01/autologin-lubuntu/
ninja_forms_form:
  - 0
tie_post_bg:
  - /wp-content/uploads/2014/01/1110-lubuntu-blue-wallpaper-with-logo1.jpg
tie_post_color:
  - 
tie_gallery_style:
  - slider
tie_link_url:
  - 
tie_link_desc:
  - 
tie_video_url:
  - 
tie_embed_code:
  - 
tie_audio_mp3:
  - 
tie_audio_m4a:
  - 
tie_audio_oga:
  - 
tie_audio_soundcloud:
  - 
tie_quote_author:
  - 
tie_quote_link:
  - 
tie_quote_text:
  - 
tie_status_facebook:
  - 
tie_status_twitter:
  - 
categories:
  - Tech
tags:
  - bitcoin
  - litecoin
  - lubuntu
  - mining
  - tech
  - ubuntu
---
If you missed setting auto login during install you can update it afterwards by modifying the following and adding in the missing lines:

**/etc/lightdm/lightdm.conf**

<pre>autologin-guest=false
autologin-user=username
autologin-user-timeout</pre>

**/etc/lxdm/default.conf**

<pre>[base]
## uncomment and set autologin username to enable autologin
autologin=username</pre>

While most guides only mentioned the later update, I found I needed to make both on Lubuntu 13.10 to get it working.