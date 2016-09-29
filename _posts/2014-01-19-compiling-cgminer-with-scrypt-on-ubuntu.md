---
id: 1330
title: Compiling CGMiner with Scrypt on Ubuntu
date: 2014-01-19T15:03:03+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1330
permalink: /2014/01/compiling-cgminer-with-scrypt-on-ubuntu/
categories:
  - Tech
tags:
  - bitcoin
  - cgminer
  - litecoin
  - mining
  - scrpyt
  - ubuntu
---
While many guides suggest using the pre-compiled versions, building from source isn't always that more troublesome and often can yield more optimized results. In that vein here's a quick guide for compiling on Ubuntu 13.10, as always milage may vary.

<pre>sudo apt-get install libcurl4-openssl-dev opencl-headers libncurses5-dev boinc-amd-opencl
cd /tmp
wget http://ck.kolivas.org/apps/cgminer/3.7/cgminer-3.7.2.tar.bz2
tar -xf cgminer*bz2

-- Download latest ADL_SDK files and extract.
cp include/* cgminer-3.7.2/ADL_SDK/
cd cgminer-3.7.2

./configure --enable-scrypt --enable-opencl 
sudo make install

-- if all went well
cgminer -n 
</pre>