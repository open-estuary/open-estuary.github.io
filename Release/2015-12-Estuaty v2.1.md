<h2><strong>Release Information:</strong></h2>
<a href="http://open-estuary.com/estuary-download" target="_blank"><u><span style="color: #0066cc;">Please click here to go to the download page of this release</span></u></a>
<pre>Release Version         : estuary-v2.1
Release Date            : 22-Dec-2015
Applications            : (Currently only for Ubuntu distribution)
    Docker v1.6.2
    Armor tools, includes perf, gdb, strace... (totally 16 tools for system debug\analyse\diagnosis）
Distributions Supported : Ubuntu 15.04 vivid, Fedora 22, OpenSuse Trumbleweed, Debian 8.2 Jessie
Kernel Version          : 4.1.6+
Bootloader Info         : UEFI + Grub 2.02
Boards Supported        : D01(ARM32), D02(ARM64), HiKey(ARM64), QEMU v2.2.0(VM on X86)</pre>
&nbsp;
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel / distribution versions / applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>1. Update build.sh script
    a. Support to build from project config file. e.g.: ./estuary/build.sh -f estuary/estuarycfg.json
    b. Enable more boards(HiKey).
    c. Enable application integration solution.
    d. Dynamically install modules\firmwares into rootfs.
2. Upgrade UEFI
    a. Resolved CPLD updating failed issue.
    b. Enabled PCIE 3.0 auto link setup.
    c. Enable HiKey board.
    d. Resolved memory reducing issues when booting from provision.
3. Upgrade kernel
    a. Enable HiKey board.
    b. Resolved random MAC address issue.
4. Firstly integrate and enable some applications.(Currently only for Ubuntu distribution)
    Notes: it will take 2--4 hours for first times reboot, depending on your network status.
    a. Armor tools, e.g.: perf, strace ...
    b. Docker v1.6.2
5. Improved some documents
6. Integrate HiBench and SysBench OLTP into Caliper.
7. Improved website
   a. Optimized bug trucker system, implement closed-loop tracking system.
   b. Provided our own ftp server, and added special binaries download page.
   c. Fixed some issues about account register on website.
   d. Added some guide about how to integrate new boards\applications int Estuary.</pre>
