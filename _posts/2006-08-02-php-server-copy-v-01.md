---
id: 262
title: PHP Server Copy V .01
date: 2006-08-02T07:14:34+00:00
author: Shinda
layout: post
guid: http://www.shindasingh.com/blog/?p=262
permalink: /2006/08/php-server-copy-v-01/
categories:
  - Tech
---
One of the biggest pains in hosting a website comes when you realize that you need to switch servers, or mirror a website. Ideally your initial server should do you just fine, but theres always those times when you find a better deal, the initial server gets hacked and you need to move, or for whatever reason you need to move your site, to another server. 

Now if your site hosts a lot of files, this can present itself to be a problem in fact become a quite cumbersome ordeal especially if you have a slow Internet connection or limited bandwidth. 

It is in that problem that lies the solution which is this script. I searched around for a bit to find a script that could help me mirror a copy of a website, but there was nothing that was simple. 

Luckily PHP can handle FTP protocol seamlessly so creating a script wasn't all that much of an ordeal. 

**<span style="FONT-SIZE: 1.2em"><strong>Usage</strong></span>** 

1) Fill out the FTP connection information 

<pre class="php"><ol>
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      &nbsp;
    </div>
  </li>
  
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      <span style="color: #0000ff;">$ftp_server</span> = <span style="color: #ff0000;">"ftp.yourftpaddress.com"</span>;
    </div>
  </li>
  
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      <span style="color: #0000ff;">$ftp_user_name</span> = <span style="color: #ff0000;">"ftp-username"</span>;
    </div>
  </li>
  
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      <span style="color: #0000ff;">$ftp_user_pass</span> = <span style="color: #ff0000;">"ftp-password"</span>;
    </div>
  </li>
  
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      <span style="color: #0000ff;">$ftp_dir</span> = <span style="color: #ff0000;">"/your/folder/here/"</span>;
    </div>
  </li>
  
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      &nbsp;
    </div>
  </li>
</ol></pre>

2) Enter the URL where you want to copy all files from ftp to.  
  


<pre class="php"><ol>
  <li style="font-family: 'Courier New', Courier, monospace; color: black; font-weight: normal; font-style: normal;">
    <div style="font-family: 'Courier New', Courier, monospace; font-weight: normal;">
      <span style="color: #0000ff;">$dirLocal</span> = <span style="color: #ff0000;">"/your/local/folder/goes/here/"</span>; 
    </div>
  </li>
</ol></pre>

\*** Make sure that the folder is writable (CHMOD 777).. 

3) Save and upload to your server. 

4) Run ftp.php by visiting the URL or running the cron job.

<span style="FONT-SIZE: 1.2em"><strong>Notes</strong></span>

The only testing this script got was when I used it to copy over all my sites from the old server over, and it worked, so theres no super bugs to report. 

This is version 1, I doubt that I'll make a version 2, and don't think that a nice front-end is necessary. After all the fact that you're responsible for copying over the site dictates that you have some degree of computer/programming knowledge. 

If the script seems to hang up then just stop the page and refresh. Script is smart enough to not replace existing files (if they match that is, and if your server supports ftp_size() );. 

No idea if file resume works. I tried to code it in, but never came abouts to testing it. 

<span style="FONT-SIZE: 1.2em"><strong>Warning</strong></span>

This script has the potential to mess up your server if used improperly. By reading and using this, you agree that I am not liable in any shape or manner for any damages and or loss of data that may occur. With that said, I don't expect the script to wreak all that much havoc on a properly configured server, however you have been warned.

<span style="FONT-SIZE: 1.2em"><strong>Download</strong></span>

<p align="left">
</p>

<p align="center">
  <a href="http://beta.shindasingh.com/wp-content/uploads/2006/08/ftp.zip"><img src="http://www.shindasingh.com/blog/wp-content/uploads/2006/08/115452730300_tn.jpg" name="115452730300.jpg" title="winzip_10_logo.jpg" height="150" width="150" alt="winzip_10_logo.jpg" border="0" id="115452730300.jpg" /> <br /> PHP Server Copy V .01</a>
</p>