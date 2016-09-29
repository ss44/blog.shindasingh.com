---
id: 1456
title: AWS Headaches Vol. 1
date: 2014-02-07T14:52:11+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1456
permalink: /2014/02/aws-server-internalerror-internal-error-on-launch-when-launching-an-ebs-booted-amazon-ec2-instance-check-your-device-name/
ninja_forms_form:
  - 0
tie_post_bg:
  - 
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
  - aws
  - hosting
  - troubleshooting
---
Ran into this problem the other night after cloning an AWS instance, and trying to use a newly minted EBS.

Launched an AWS instance and got:

<pre>Server.InternalError: Internal error on launch</pre>

Luckily thanks to the internets and google came across the solution on:

[Ville's Corner: Did you get "Server.InternalError: Internal error on launch" when launching an EBS-booted Amazon EC2 instance? Check your device name...](http://www.villescorner.com/2011/12/did-you-get-serverinternalerror.html).

and turned out just needed to switch:

<pre>/dev/sda</pre>

to

<pre>/dev/sda1</pre>