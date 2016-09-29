---
id: 1934
title: Vagrant Auto Install Plugins
date: 2015-02-06T02:14:40+00:00
author: Shinda
layout: post
guid: https://blog.shindasingh.com/?p=1934
permalink: /2015/02/vagrant-auto-install-plugins/
ninja_forms_form:
  - 0
tcwp_meta_box_creator:
  - 
tcwp_meta_box_cust_img:
  - 
tcwp_meta_box_d1:
  - 
tcwp_meta_box_d1l:
  - 
tcwp_meta_box_d2:
  - 
tcwp_meta_box_d2l:
  - 
tcwp_gallery_0:
  - 
tcwp_gallery_1:
  - 
tcwp_gallery_2:
  - 
tcwp_gallery_3:
  - 
tcwp_meta_box_player:
  - 
tcwp_meta_box_player_w:
  - 
tcwp_meta_box_player_h:
  - 
tcwp_meta_box_player_str:
  - 
tcwp_meta_box_player_str_c:
  - 
tcwp_meta_box_cust_desc:
  - 
tcwp_meta_box_select:
  - summary_large_image
app_iphone_id:
  - 
app_iphone_url:
  - 
app_iphone_name:
  - 
app_ipad_id:
  - 
app_ipad_url:
  - 
app_ipad_name:
  - 
app_ios_country:
  - 
app_gplay_id:
  - 
app_gplay_url:
  - 
app_gplay_name:
  - 
tcwp_meta_box_check:
  - off
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
tie_status_instagram:
  - 
xyz_fbap:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
categories:
  - Programming
  - Tech
tags:
  - deploying
  - programming
  - ruby
  - vagrant
---
[Vagrant](https://www.vagrantup.com/) is an awesome tool to get up and running on any project quick and easy. Theoretically, making the days of manually setting up a new project, configuring host files, and figuring out the needed dependencies a thing of the past at least for all new members inheriting or taking on a project.

Unfortunately while Vagrant is sold as getting and sharing a project with other devs as simple as having them run, _vagrant up_, this falls short when needing to work with any vagrant plugins at which time each user has to install the needed plugins to get up and running.

On the bright side since Vagrant files are just ruby this can be quickly solved with a bit of added logic - particularly,

<noscript>
  <pre><code class="language- ">required_plugins = %w( vagrant-hostsupdater vagrant-vbguest )

_retry = false
required_plugins.each do |plugin|
  unless Vagrant.has_plugin? plugin
    system "vagrant plugin install #{plugin}" 
    _retry = true
  end
end

if (_retry)
  exec "vagrant " + ARGV.join(' ')
end
</code></pre>
</noscript>