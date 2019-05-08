---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Documents
---

<h1><strong>Introduction</strong></h1>
This documentation describes how to get, build, deploy and bring up target system based Estuary Project, it will help you to make your Estuary Environment setup from ZERO.

All following sections will take the D05 board as example, other boards have the similar steps to do, for more detail difference between them, please refer to <a href="https://open-estuary.github.io/tags/#Hardware%20Boards" target="_blank">Hardware Boards</a> sections in this website.
<h1 id="title2"><strong><span id="preparation">Preparation
</span></strong></h1>
<h2>Prerequisite</h2>
<strong>Host machine:</strong> Ubuntu (newer than 12.04) or CentOS (newer than 7) to download and build estuary.

<strong>Hardware boards:</strong>  Target boards based on ARM32 or ARM64, to deploy or run target binaries. Now, we have already validated  <a style="color: #008000;" href="https://open-estuary.github.io/2016/08/30/d05-board/">D05 board,</a><span style="color: #008000;"> <a style="color: #008000;" href="https://open-estuary.github.io/2018/07/25/d06-board/">D06 board</a></span>. If you just try it on QEMU, the hardware boards are not necessary.

If you work on a real hardware board based on ARM SoC, follows should be available too.
<h2 id="title4"><span id="build">Get &amp; Build Estuary yourself</span></h2>
<p class="disqus">You can refer to <a href="https://open-estuary.github.io/2015/09/08/getting-started/">getting started</a> to get and build the whole project <code> </code></p>
<p class="disqus">For more detail release notes, please refer to the <b>changelist.md </b>in <a href="https://github.com/open-estuary/estuary" target="_blank"><span style="color: #008000;">Estuary Source Repo</span><b>.</b></a></p>

<h2 id="title6"><span id="binary">Use binaries directly</span></h2>
<p class="disqus">Anyway, before booting up system, all binaries should be available firstly.</p>
<p class="disqus">You can get them yourself as above description.</p>
<p class="disqus">In fact, there are all built binaries and the corresponding documents according to above description for each released version for downloading freely, you can get them from <a href="https://open-estuary.github.io/2015/11/16/binary-download/"><span style="color: #339966;">Binary Download</span> </a>according to the right release version and board type directly.</p>

<h1 id="title7"><strong><span id="bringup">Bring up System</span></strong></h1>
<p class="disqus">We provide so many different methods to bring up system with the corresponding binaries, you can get more detail documentations about it in <span style="color: #ff0000;"</span> directory after building as above, or download the appropriate documents directly from following position according to the right release version and board type.</p>
<p class="disqus">Download-RootFolder/release/&lt;version&gt;/linux/common/&lt;board type&gt;/documentation</p>
Accessing from China: <strong>Download Location</strong> is:<span id="im-content_1471420632351" class="im-content"><a href="ftp://117.78.41.188/pre-releases">ftp://117.78.41.188</a></span>
