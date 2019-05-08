<h2><strong>Release Information:</strong></h2>
<a href="https://open-estuary.github.io/2015/11/16/binary-download/"target="_blank"><u>Please click here to go to the download page of this release</u></a>
<pre>Release Version         : v3.0
Release Date            : 14-Mar-2017
Applications            : (For all supported distributions)
   QEMU                 : v2.8.0
   OpenJDK              : v1.8
   Docker               : v1.6.2
   MySQL                : percona-5.6.22-72.0
   Armor tools          : include perf, gdb, strace... (totally more than 40 tools for system debug\analyses\diagnosis）
Distributions Supported : Ubuntu 16.04 Xenial Xerus, Fedora 22, OpenSuse Trumbleweed, Debian 8.5.0, CentOS 7.3.1611, MiniOS 1.1
Kernel Version          : 4.9.20
Bootloader Info         : UEFI 3.0 + Grub 2.02-beta3
   Boot mode            : PXE, NFS, SATA, SAS, USB, USB CDROM
Boards Supported        : D03(ARM64), D05(ARM64), QEMU v2.8.0(VM on X86)
Deployment Methods      : Manual binaries, Auto USB disk, Auto ISO file both by web or VGA monitor, Auto PXE</pre>
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel /distribution versions/applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>Change list for Estuary v3.0:

1. Hardware boards support
    - Supported D05 board(Hi1616) officially
    - Supported D03/D05 boards based on ACPI
    - Added basic support for AMD Overdrive board
2. UEFI
    - Upgraded UEFI version to 16.12 Release
    - Added support for BMC boot device ipmi protocol
    - Fixed 2TB+ disk support bug
3. OS
    - Upgraded Linux kernel version to v4.9.0 (based on Linaro ERP 16.12)
    - Removed DT(Device Tree) support all boards
    - Added support for more PCIe devices in D03/D05: SSD, RAID(LSI 2308/3008/3108), Intel 82599 NIC
    - Supported CentOS native build for open-estuary source
    - Supported NUMA on D05 board officially
    - Support Perf L3 cache / MN features
4. Distros
    - Improved mini-rootfs for better Lmbench stream performance
    - Upgraded CentOS AltArch to 7.3
    - Upgraded Ubuntu to 16.04
    - Fixed DHCP boot conflict issue when passing ip=dhcp in kernel command line
5. Applications
    - Upgraded QEMU to v2.8.0
    - Enabled OpenJDK 1.8
    - Enabled MySQL(Percona Server) docker image
    - Enabled Redis docker image
    - Enabled PostgreSQL docker image
6. Deployment
    - Supported USB Flash disk script-type installation
    - Supported BMC load ISO both by web or VGA monitor
    - Supported multiple distros in USB install Disk method
7. Website
    - News Scroller added
    - New Collaboration Feature added
    - New Technical support platform added
8. Document
    - Added D05 documents and update all project documents
9. Caliper
    - Support of CentOS
    - Email feature added
    - Upgraded several benchmarking tools (Iperf, Hibench)
    - Several bug fixes and improvements (sysbench, parser, execution options, etc)</pre>
<h2><b>Known issues</b>:</h2>
<pre>1. Armor utilities are not fully support</pre>
