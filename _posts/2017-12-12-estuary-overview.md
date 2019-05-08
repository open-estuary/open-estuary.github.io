---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Documents
---

<h1><span style="color: #008000;"><strong>Estuary: A complete open source solution for ARM based systems<a href="">
</a></strong></span></h1>
<span style="color: #0000ff;"><span style="color: #000000;"><strong>Estuary is a complete open source project for ARM64 ecosystem</strong></span>.</span> It provides a total solution for general-purpose computer based on aarch64 architecture. Anyone can quickly bring up an ARM64 platform - both software and hardware with Estuary!

May be you are just a user to ARM64 computer or a community developer who works on aarch64 platform, or a student or scholar working on ARM64 hardware in university… anyway, no matter whoever you are, wherever you are, so long as you want to work, develop, debug, estimate, validate on an ARM64 platform, <span style="color: #000000;"><strong>Estuary is for you!</strong></span>

<span style="color: #000000;">So get started with Estuary and explore various features and tools which we support for your ARM64 platform</span>...
<h2>Main Targets:</h2>
<p class="disqus">The major goals for Estuary project are:</p>

<ol class="disqus">
    <li>A stable\available quick start solution based on ARM64 computer, so that anyone can easily get and bring up the complete development environment, so that you can just focus on your particular field quickly.</li>
	<li>A common basic platform, which should be sustainable and will be continuously improved, can attract\absorb and integrate all 3rd part achievement ceaselessly.</li>
	<li>Sufficient technological documentation, so that any user or partner can easily get useful help from it.</li>
	<li>Simple and effective communication forum for ARM64 ecosystem, so that users can interact and share each other to improve ARM64 ecosystem.</li>
	<li>A bug tracking system, so that anyone can raise, track and help to resolve the issues, this will help to mature the solution and enhance the ecosystem.</li>
	<li>Multiple ARM64-based hardware platforms, and related software to speed up the ARM64 ecosystem development.</li>
</ol>
The most key goal of Estuary project is to support, enable and speed up the maturity of ARM64 ecosystem.

&nbsp;
<h2>Architecture Overview:</h2>
<p class="disqus">The high level view for Estuary is as given below:</p>
<p class="disqus"><img class="aligncenter size-large wp-image-1562" src="https://raw.githubusercontent.com/open-estuary/open-estuary.github.io/master/img/arch1-1024x600.png" alt="arch" width="1024" height="600" /></p>

<div class="fluidbox-wrap">All major components shown above are described as below:</div>
<div class="fluidbox-wrap">
<ol class="disqus">
	<li>
<p class="disqus"><strong>Hardware boards:</strong>
A variety of boards based on ARM64 SoC will be enabled and integrated by Estuary, no matter which company produce it, so long as the board is designed based on ARM64 SoC, all of them will be encouraged to be integrated into this solution. Now we can support<a style="color: #0066cc;" href="https://open-estuary.github.io/2016/08/30/d05-board/">D05 board,</a><span style="color: #008000;"> <a style="color: #008000;" href="https://open-estuary.github.io/2018/07/25/d06-board/">D06 board</a></span>.</p>
</li>
	<li>
<p class="disqus"><strong>UEFI, BMC &amp; cpld:</strong></p>
Multi-kinds of firmware will be enabled for Estuary, include but not limited to UEFI\BMC, CPLD.
More detail about UEFI and other firmware, please refer to the documents in https://github.com/open-estuary/estuary/tree/master/doc/release-files/binary/.
<p id="tips"><em><strong>Download-Rootfolder</strong></em></p>
https://github.com/open-estuary/estuary-uefi</li>
	<li>
<p class="disqus"><strong>Operation System:</strong>
Two main kinds of OS will be enabled, one is based on Windows, another is based on Linux. For Linux OS, not only the latest kernel will be enabled for Estuary, various distributions will be enabled for it too, include but not limited to Ubuntu, Fedora, OpenEmbedded, Debian, Redhat and etc.</p>
<p class="disqus">The linux kernel source can be obtained by  <strong>git clone <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://github.com/open-estuary/kernel" target="_blank">https://github.com/open-estuary/kernel.git</a></span></strong></p>
<p class="disqus">All prebuilt kernel image\dtb\grub and other binaries can be obtained in Download-Rootfolder/release/&lt;version&gt;/linux/common/&lt;board type&gt;/.
All validated distributions can be obtained in Download-Rootfolder/release/&lt;version&gt;/linux/&lt;distro name&gt;/common.
More detail documentations are available in Download-Rootfolder/release/&lt;version&gt;/linux/common/&lt;board type&gt;/documentation.</p>
</li>
	<li><strong>Virtualization Technologies:</strong>
Multi-kinds of virtualization technologies will also be enabled for Estuary, e.g.:<span style="color: #0066cc;"><a style="color: #0066cc;" href="https://www.docker.com/" target="_blank" rel="external">Docker</a></span>\<span style="color: #0066cc;"><a style="color: #0066cc;" href="https://linuxcontainers.org/" target="_blank" rel="external">Lxc</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://www.linux-kvm.org/page/Main_Page" target="_blank" rel="external">KVM</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://www.xenproject.org/" target="_blank" rel="external">Xen</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://wiki.qemu.org/Main_Page" target="_blank" rel="external">Qemu</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://www.openstack.org/" target="_blank" rel="external">OpenStack\swift</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://www.vmware.com/" target="_blank" rel="external">Vmware, HHVM</a></span> or <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://www.cloudfoundry.org/" target="_blank" rel="external">CloudFoundry</a></span> and so on.</li>
	<li><strong>Middle Ware Components:</strong>
In order to work as a universal server based on ARM64 machine, some common cloud platform services are necessary. e.g.: <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://ceph.com/" target="_blank" rel="external">Ceph</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://hadoop.apache.org/" target="_blank" rel="external">Hadoop</a></span>, <span style="color: #3366ff;"><a style="color: #3366ff;" href="http://spark.apache.org/">Spark</a></span> and so on. Some basic components will be enabled for Estuary, e.g.: <span style="color: #3366ff;"><a style="color: #3366ff;" href="http://httpd.apache.org/" target="_blank" rel="external">Apache</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://www.mysql.com/" target="_blank" rel="external">MySQL</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://mariadb.org/" target="_blank" rel="external">MariaDB</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://www.postgresql.org/" target="_blank" rel="external">PostgreSQL</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://www.python.org/" target="_blank" rel="external">Python</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://www.opendataplane.org/" target="_blank" rel="external">ODP</a></span>, <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://openjdk.java.net/" target="_blank" rel="external">OpenJDK</a></span> and etc. Currently Armor, OpenJDK, Docker, Docker App and OpenStack have enabled in Estuary. For details, please refer to <span style="color: #3366ff;"><a style="color: #3366ff;" href="https://github.com/open-estuary/estuary/blob/master/doc/Packages_Manual.md">Packages_Manual.md</a></span>.</li>
	<li><strong>Typical Applications:</strong>
To use easily, some typical applications should be enabled too, like Web server, Big data retrieve, Cloud storage, Cloud machine and etc.</li>
	<li><strong>Peripheral Tools:</strong></li>
</ol>
<p style="padding-left: 60px;">Good peripheral support tools are very important factors too for a total solution, in this project, they are:</p>
<p style="padding-left: 60px;">A. Tool Chain: Cross complier and different compilers. More detail refer to <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://releases.linaro.org/components/toolchain/" target="_blank" rel="external">Tool Chains</a></span>.<br>B. Open Board Laboratory: To provide a way to remote access, debug hardware board. More detail refer to <a href="https://open-estuary.github.io/2015/08/21/accessing-boards-in-open-lab/"><span style="color: #0066cc;">accessing boards in open lab document</span>.</a><br>C. Website: Just this website, news publish, technological communication, all release information, customer support, documentation release, mail list service, wiki and etc.<br>D. LAVA system: Automated test and job validation system. More detail please refer to <a href="http://114.119.4.74:800/" target="_blank"><span style="color: #0066cc;">LAVA</span>.</a></p>

</div>
<p class="disqus">In above picture, <span style="color: #339966;">green block</span> with <span style="color: #ffcc00;">yellow</span> border means they will be enabled by default by quick start. The <span style="color: #339966;">green block</span> means all these functions will be implemented in Estuary later versions, <span style="color: #808080;">grey block</span> means options which will be implemented later.</p>

<h2 id="tips">Download-Rootfolder</h2>
Accessing from China: <a href="ftp://117.78.41.188/">ftp://117.78.41.188/</a>

Accessing from outside-China:
<h2 class="disqus">Getting Started</h2>
If you want to get started fast with source code, please refer <span style="color: #0066cc;"><a style="color: #0066cc;" href="https://open-estuary.github.io/2015/09/08/getting-started/" target="_blank">Getting Started</a></span> document.
If you just want to get started quickly with binaries directly, please refer <span style="color: #3366ff;"><a style="color: #3366ff;" href="http://open-estuary.github.io/2015/11/16/binary-download/">Binary Download</a></span>.
<p class="disqus">To get\build\bring up estuary completely, please refer to <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://open-estuary.github.io/2015/08/24/estuary-user-manual/">Estuary User Manual</a></span>.
To post or search any technological information about estuary, please refer to <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://open-estuary.org/forums/" target="_blank">Discussion Forum</a></span>.
To raise new issues about estuary, please refer to <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://open-estuary.org/issue-tracker/">Issue Tracker</a></span>.
Enjoy Estuary and provide us your <span style="color: #0066cc;"><a style="color: #0066cc;" href="http://open-estuary.org/contact-us/" target="_blank">Feedback and Suggestions</a></span>.</p>
<p class="disqus">And....if you have any ARM based platform ...and you want to enable Estuary solution on it?
Please <a href="http://open-estuary.org/contact-us/" target="_blank"><span style="color: #0066cc;">contact us</span>!</a> Let's work together to make the ARM Server Ecosystem Rich and Matured!
Yes, together we can make it happen!</p>
