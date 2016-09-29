---
id: 1798
title: Issues Installing XCode 6.1
date: 2014-11-18T22:29:46+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1798
permalink: /2014/11/issues-installing-xcode/
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
xyz_fbap:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
categories:
  - Apple
  - Tech
tags:
  - apple
  - fix
  - osx
  - troubleshooting
---
Recently encountered the issue where while trying to install XCode 6.1, I got the following: "item temporarily unavailable"

Seems to have been a common problem but not many common solutions. Some relying on downloading 3rd party apps, others on just kicking your mac hard enough that it worked.

Fortunately the following worked for me:

Quit/force-quit "storeagent" and App Store processes. Then in a terminal run:

 `Recently encountered the issue where while trying to install XCode 6.1, I got the following: "item temporarily unavailable"

Seems to have been a common problem but not many common solutions. Some relying on downloading 3rd party apps, others on just kicking your mac hard enough that it worked.

Fortunately the following worked for me:

Quit/force-quit "storeagent" and App Store processes. Then in a terminal run:

` 

Restart the App Store and click update. Everything was good to go.

(Note at the time I'm still currently running OSX Mavericks).

Solution found @ <a href="https://groups.google.com/forum/#!topic/macenterprise/KxeIuCT5y0U" target="_blank">https://groups.google.com/forum/#!topic/macenterprise/KxeIuCT5y0U</a>.

Alternatively you can always manually download XCode from the Apple Developer Site: <a href="https://developer.apple.com/downloads/index.action?name=Xcode" target="_blank">https://developer.apple.com/downloads/index.action?name=Xcode</a>