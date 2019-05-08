<h2><strong>Release Information:</strong></h2>
<a href="https://open-estuary.github.io/2015/11/16/binary-download/"target="_blank"><u>Please click here to go to the download page of this release</u></a>
<pre>Release Version         : v3.1
Release Date            : 31-May-2017
Openstack               : Support Openstack Newton version which based on Linaro ERP1612
   QEMU                 : v2.8.0
   OpenJDK              : v1.8
   Docker               : v1.6.2
   MySQL                : percona-5.6.22-72.0
   CI                   : Support NFS/SAS boot testing on D03/D05 board（OS is Ubuntu or CentOS）
   Armor tools          : include perf, gdb, strace... (totally more than 40 tools for system debug\analyses\diagnosis）
Distributions Supported : Ubuntu 16.04 ,CentOS 7.3.1611,Debian 8.5.0,Fedora 22,OpenSuse tumbleweed,Rancher 1.0.0,OpenEmbedded 2.0,mini-rootfs 1.1
Kernel Version          : 4.9.20
Bootloader Info         : UEFI 3.0 + Grub 2.02-beta3
   Boot mode            : PXE, NFS, SATA, SAS, USB, USB CDROM
Boards Supported        : D03(ARM64), D05(ARM64), QEMU v2.8.0(VM on X86),HiKey
Deployment Methods      : Manual binaries, Auto USB disk, Auto ISO file both by web or VGA monitor, Auto PXE</pre>
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel /distribution versions/applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>1. UEFI
	- Added HiKey support in UEFI
2. OS
	- Upgraded Linux kernel version to v4.9.20
	- Supported HiKey with v4.9.20 kernel
3. Distros
	- Fixed minirootfs devramfs confliction with mdev
	- Added support for OpenEmbedded
	- Added support for RancherOS
4. Applications
	- Added OpenStack Newton initial support
	- Enabled HHVM for ARM64
	- Enabled MongoDB docker image
5. Deployment
	- Fixed various BMC load ISO bugs (distro selection, waiting time)
	- Sort hard disk list in alphabetic order
	- Improved distribution generation speed when building
6. Document
	- Updated project documentation (Readme, Grub, etc)
	- Updated applications user manual (Redis, PostgreSQL, MySQL, MongoDB, etc)
7. CI/Automation
	- Supported basic CI/Automation for D05 (Build, NFS/Hard disk Deployment, Some tests)
	- Supported basic  CI/Automation for D06 (Build, NFS/Hard disk Deployment, Some tests)
</pre>
<h2><b>Known issues</b>:</h2>
<pre>Armor utilities are not fully support</pre>
