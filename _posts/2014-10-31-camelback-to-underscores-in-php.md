---
id: 1751
title: camelBack to underscores in PHP
date: 2014-10-31T21:37:43+00:00
author: Shinda
layout: post
guid: http://blog.shindasingh.com/?p=1751
permalink: /2014/10/camelback-to-underscores-in-php/
xyz_fbap:
  - 1
ninja_forms_form:
  - 0
snap_MYURL:
  - 
snapEdIT:
  - 1
categories:
  - PHP
  - Programming
---
Basically takes:

thisStringHere and turns it into - this\_string\_here.

<noscript>
  <pre><code class="language-php php">&lt;?php

/** 
 * Convert Camelback strings to underscore string.
 * @param String to convert 
 * @return String String in underscore format.
 */
function camelToUnderscores($str){
	// First let's just add in the appropriate "_";
	$newStr = '';
	// Loop over the string characters
	for ($x = 0; $x &lt; strlen($str); $x++){
		// Check if the current letter is capital
		if ($x &gt; 0 && ord($str[$x]) &gt;= 65 && ord($str[$x]) &lt;= 90){
			$newStr .= "_" . $str[$x];
		}else{
			$newStr .= $str[$x];
		}
	}

	return strtolower($newStr);
}
</code></pre>
</noscript>