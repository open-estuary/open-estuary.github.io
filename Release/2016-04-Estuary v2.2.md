<h2><strong>Release Information:</strong></h2>
<a href="http://open-estuary.com/estuary-download" target="_blank"><u>Please click here to go to the download page of this release</u></a>
<pre>Release Version         : estuary-v2.2
Release Date            : 27-Apr-2016
Applications            : (For all supported distributions)
   Docker               : v1.6.2
   ODP                  : v1.2
   MySQL                : percona-5.6.22-72.0
   Armor tools          : include perf, gdb, strace... (totally more than 40 tools for system debug\analyse\diagnosis）
Distributions Supported : Ubuntu 15.04 vivid, Fedora 22, OpenSuse Trumbleweed, Debian 8.2 Jessie, CentOS 7
Kernel Version          : 4.4 
Bootloader Info         : UEFI 2.2 + Grub 2.02
   Boot mode            : ESL(exclude D01), Flash(exclude D03), PXE, NFS, SATA, SAS(exclude D01), USB(exclude D01), USB CDROM(exclude D01)
Boards Supported        : D01(ARM32), D02(ARM64), D03(ARM64), HiKey(ARM64), QEMU v2.2.0(VM on X86)
Deployment Methods      : Manual binaries, Auto USB disk(exclude D01), Auto ISO file(exclude D01), Auto PXE(exclude D01)</pre>
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel /distribution versions/applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>1. Formally support D03 based on DTS.
2. Completely compatible for HiKey\D01\D02 and D03 boards.
3. Firstly support booting system from SAS disk for D02 by default.
4. Upgraded kernel to v4.4.
5. Partly enabled ACPI (Only D02).
6. Improved build script:
    * Support native building.
    * Support both USB-Disk\CD-ISO installation methods.
    * Support automatic PXE environment setup.
    * Support to terminate and restart build task during building.
7. Improved mini-rootfs to support more useful commands.
8. Enabled CentOS firstly.
9. Firstly integrated ODP and MySQL into Estuary.
10. Added collaboration feature in website.
11. Enabled Docker &amp; Armor tools for all distributions.
12. Improved all documents, and change them into markdown format.
13. Fixed most issues found in rc0 &amp; rc1, include but not limited to: UEFI, network, grub, usb compatibility, build and etc.
14. Support D01 better, to enable boot from NorFlash, PXE, SATA.
15. Enable both 32bits and 64bits minirrotfs for different arch.
16. Improved Caliper as follows:
    * Fixes and improvements in the Caliper Report html and in graphs:
    * New sections, titles added in the report to make the report more detailed, still few hardcoded information are present, to be improved in further releases.
    * New features (like caliper -c option), NFS interface for test log capture are added and existing configuration options of test tools modified as required.
    * Tinymembench memory benchmarking has been added for memory benchmarking.
     Many small improvements and bug fixes.
</pre>
<h2><b>Remained issues</b>:</h2>
<pre>1. ACPI is not available for D03 yet.
2. KVM is not available based on kernel v4.4 yet.
3. PCIE-SATA card can't work well on D03.
4. SATA is very unstable on D02 board.</pre>
