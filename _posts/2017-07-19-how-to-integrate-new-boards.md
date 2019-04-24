---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags: 
    - Documents
---

This page is to guide user how to integrate their new board into Estuary, and what are the prerequisites for the integration.
If you want to integrate your new board into Estuary, <a href="https://github.com/open-estuary/estuary/issues/new" target="_blank">please contact us</a>.
<h2>Hardware Prerequisites</h2>
1. ARM32\ARM64 based SoC

2. At least one debug UART port
3. At least one Ethernet network RJ45 port
4. General power supplier socket
5. Main memory size &gt; 1G bytes
6. Secondary storage size &gt; 10G bytes
<h2>Software Prerequisites</h2>
<br>1. Available UEFI based on Linaro UEFI 2015.05(or latest Tiano EDK UEFI) with full open source</br>
<br>a. Enable UEFI self-upgrade</br>
<br>b. Boot from Secondary storage by grub</br>
<br>c. Boot from PXE by grub</br>
<br>d. ACPI available</br>
<br>2. Available kernel based on linux-4.1.6 with full open source</br>
<br>a. Enable arch with basically available components e.g.: timer\interrupt\UART</br>
<br>b. Enable all special peripheral drivers</br>
<br>c. Support device configuration by both ACPI &amp; dts</br>
<h2>Others Requirements</h2>
1. UEFI &amp; Kernel engineers for co-work debug and UEFI\kernel upstreaming

2. The corresponding technological documentations about: UEFI\kernel building\upgrading, system deployment.
<h2>Integration Steps</h2>
<br>1. Prepare your hardware &amp; software according to above description.</br>
<br>2. <a href="https://github.com/open-estuary/estuary/issues/new" target="_blank">Please contact us</a> to co-work and debug.</br>
<br>3. Integrate &amp; push to Estuary for next version release.</br>
