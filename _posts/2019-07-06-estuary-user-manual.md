---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
---
# Introduction
---

This documentation describes how to get, build, deploy and bring up target system based Estuary Project, 
it will help you to make your Estuary Environment setup from ZERO.

All following sections will take the D05 board as example, other boards have the similar steps to do, 
for more detail difference between them, please refer to 
[Hardware Boards](https://open-estuary.github.io/tags/#Hardware%20Boards) sections in this website.

---


# Preparation

## 1. Prerequisite
---
**Host machine**: Debian (newer than 9.6) or CentOS (newer than 7.6) to download and build estuary.

**Hardware boards**: Target boards based on ARM64, to deploy or run target binaries. 
Now, we have already validated  
[D05 board](https://open-estuary.github.io/2016/08/30/d05-board/), 
[D06 board](https://open-estuary.github.io/2018/07/25/d06-board/). 

*If you just try it on QEMU, the hardware boards are not necessary.*

If you work on a real hardware board based on ARM SoC, follows should be available too.

---

## 2. Get & Build Estuary yourself
---
You can refer to [getting started](https://open-estuary.github.io/2015/09/08/getting-started/) to get 
and build the whole project.

*For more detail release notes, please refer to the 
[Release Lists](https://open-estuary.github.io/2019/06/29/releases/)*

---

## 3. Use binaries directly
---
Anyway, before booting up system, all binaries should be available firstly.

packages:
[appliaction](http://203.160.91.226:18083/repodata/releases/5.0/) 
[kernel](http://203.160.91.226:18083/repodata/releases/5.2/)

You can get them yourself via above link.

In fact, you can install these packages directly by yum/apt tools while using the 
[relesed ISO image](ftp://117.78.41.188/releases/).

---

# Bring up System
---
We provide so many different methods to bring up system with the corresponding binaries, 
you can get more detail documentations about it in directory after building as above, 
or download the appropriate documents directly from following position according to the right 
release version and board type. 

You can get deploy documentation as follows:

[Deploy Documentation](https://github.com/open-estuary/estuary/blob/master/doc/Deploy_Manual.4All.md)

---
