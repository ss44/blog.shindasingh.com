---
id: 1313
title: Mining Rig Troubleshooting
date: 2014-01-14T06:34:51+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1313
permalink: /2014/01/mining-rig-troubleshooting/
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
  - litecoin
  - Tech
---
While putting together my mining rig I ran into a few hurdles which I figured I'd share the solutions for, since google either proved futile, or there were so often much advice that just didn't apply.

GA-F2A88X-D3H Motherboard crashing whenever a PCI card is added to the 4x slot

  * In my case this turned out to be old firmware. Upgraded V3 and things seemed to work.

CGMiner won't Autostart on Launch.

  * There's a few scripts out there that claim to solve this problem, unfortunately none of the commonly recommended solutions worked for me. Of the tips that **didn't work** included: 
      * adding : @crontab sleep 30; start_miner.sh
      * adding "start_miner.sh" entry in /etc/rc.local.
    
    I'm guessing both failed since cgminer relies on xserver to be started, before the ATI drivers themselves are initialized. Workaround was:
    
      * Soon as I test it i will post the script & paths here

Can't get ati drivers configured on ubuntu-server:

  * ATI drivers require X  server so really the mistake was trying to install the server edition. Use a desktop version and all should be good.

Motherboard doesn't have a power button

  * You can short your own button using a pen, paperclip, screwdriver, by touching it with the 2 pins where the power button connection would normally go.
  * You should change your bios settings so that the PC auto starts soon as it has power, to avoid needing to do this every time and to also automate things.

&nbsp;