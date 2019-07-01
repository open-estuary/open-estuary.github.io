---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Releases
---
<h2><strong>Release Information:</strong></h2>
<a href="https://open-estuary.github.io/2015/11/16/binary-download/"target="_blank"><u>Please click here to go to the download 
page of this release</u></a>
<pre>Release Version         : 5.10
Release Date            : 29-June-2019
Application support     : https://github.com/open-estuary/distro-repo/blob/master/docs/packages_list_5.10.md
   CI                   : Support NFS/PXE boot testing on D05/D06 boards CentOS & Debian
   Armor tools          : include malluma, perf, gdb, strace... 
Distributions Supported : CentOS 7.5,Debian 9
Kernel Version          : 4.19.5
Bootloader Info         : 
   TaiShan2280          : UEFI 1.58 + Grub 2.02-beta3
   D06                  : UEFI 3.03 + Grub 2.02-beta3
Boot mode               : PXE, NFS, iBMC Load ISO
Boards Supported        : D05(ARM64), D06(ARM64)
Deployment Methods      : Auto ISO file load, PXE</pre>
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel /distribution versions/applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>
  1. UEFI
       - N/A
  2. OS
       - N/A
  3. Distros
       - N/A
  4. Applications
       - Added benchmark tools : rt-tests, pipework, netperf, ycsb
       - Added virtualization tools : qemu
       - Added cloud tools : mariadb, postgreSQL, elasticsearch, redis, mongodb, nginx, lamp
       - Added other tools : N/A
  5. Armor tools
       - N/A 
  6. Deployment
       - Support standard network installation, ISO installation, and compatible with the original NFS deployment
       - Build scripts support parallel compiling of CentOS, Debian and common modules     
  7. Document
       - N/A
  8. CI/Automation
       - Supported basic CI/Automation for D05 (Build, NFS/PXE Deployment, Some tests)
       - Supported basic CI/Automation for D06 (Build, NFS/PXE Deployment, Some tests)</pre>
  <h2><b>Known issues</b>:</h2>
  <pre>
  1. cannot use sendme tool in rt-tests because backfire module compile failed with 4.19 kernel's API
  2. QEMU dynamic migration test failed
  </pre>