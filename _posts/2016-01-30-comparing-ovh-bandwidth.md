---
id: 2061
title: Comparing OVH Bandwidth
date: 2016-01-30T20:04:59+00:00
author: Shinda
layout: post
guid: https://blog.shindasingh.com/?p=2061
permalink: /2016/01/comparing-ovh-bandwidth/
xyz_fbap:
  - 1
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
snap_MYURL:
  - 
snapEdIT:
  - 1
categories:
  - Tech
---
Wanting to move my Plex Library to the cloud, I came across OVH as a

OVH is a European / Canadian hosting provider with some cheap hosting rates, and a direct competitor to AWS. They offer a object storage that rivals Amazon's S3 and at time of writing is cheaper.

AWS - $0.0300/GB (USD) vs OVH - 0.0125/GB (CAD) making it seemingly ideal for media storage.

However one of the confusing parts is comparing OVH's various and seemingly similar hosting options and how they interact with there Object Store. The following findings compared OVH's VPS Cloud 2 and Elastic Cloud -EG-7 plans.

<table style="height: 51px;" width="531">
  <tr>
    <th>
      Test
    </th>
    
    <th>
      VPS Cloud 2
    </th>
    
    <th>
      EG-7
    </th>
  </tr>
  
  <tr>
    <td>
      Downloading 862 MB/file
    </td>
    
    <td>
      1m23.665s
    </td>
    
    <td>
      0m43.634s
    </td>
  </tr>
  
  <tr>
    <td>
      Downloading 862 MB/file 2nd Time
    </td>
    
    <td>
      0m13.935s
    </td>
    
    <td>
      0m1.097s
    </td>
  </tr>
  
  <tr>
    <td>
      Downloading 862 MB/file 3rd Time
    </td>
    
    <td>
      0m6.872s
    </td>
    
    <td>
      0m1.239s
    </td>
  </tr>
  
  <tr>
    <td>
      Uploading 1 GB file
    </td>
    
    <td>
      0m30.891s
    </td>
    
    <td>
      0m18.476s
    </td>
  </tr>
  
  <tr>
    <td>
      Uploading 1 GB file 2nd Run
    </td>
    
    <td>
      4m1.514s
    </td>
    
    <td>
       N/A
    </td>
  </tr>
</table>

  * Transfers were completed using s3ql mounted as:`mount.s3ql --authfile /etc/s3qlcreds.txt --allow-other swiftks://auth.cloud.ovh.net/BHS1:test /media/test`
  * Results measured using the following:Download: `time cp /media/test/download.bin ~/`
  
    Upload: `time cp ~/upload.bin /media/test/`
  * Sample upload file generated using: `openssl rand -out sample.bin -base64 $(( 2**30 * 3/4 ))`

&nbsp;