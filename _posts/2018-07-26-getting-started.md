---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Documents
---

<a><img class="aligncenter size-full wp-image-455" src="https://raw.githubusercontent.com/open-estuary/open-estuary.github.io/master/img/gettingstarted1.png" alt="gettingstarted" width="270" height="253" /></a>

<span style="color: #ff0000;">Supposedly, you are working on Ubuntu (newer than 12.04) or CentOS (newer than 7)!</span>
Please execute the following command to update.
For Ubuntu system:
<pre>$ sudo apt-get update; sudo apt-get upgrade -y; sudo apt-get install -y wget git</pre>
For CentOS system：
<pre>$ sudo yum update -y; sudo yum install -y wget git</pre>
<h2><strong>Download And Build</strong></h2>
Firstly, to download estuary sources with the following command.
<pre>$ git clone https://github.com/open-estuary/estuary.git</pre>
<p class="disqus">Secondly, you can build the whole project with the default config file as following command:</p>

<pre>$ cd estuary
$ sudo ./build.sh --build_dir=./workspace
</pre>
<p class="disqus"> To try more different build on estuary, please get help information about build.sh as follow:</p>

<pre>$ ./build.sh -h</pre>
More detail user guide about this project, please refer to <span style="color: #008000;"><a style="color: #008000;" href="https://open-estuary.github.io/2018/10/04/estuary-user-manual/">Estuary User Manual</a></span>.

If you just want to quickly try it with binaries, please refer to our binary <strong>Download Page </strong>to get the latest binaries and documentations for each corresponding boards.

Accessing from China: <span id="im-content_1471420632351" class="im-content"><a href="ftp://117.78.41.188/releases">ftp://117.78.41.188</a></span>
