<h2><strong>Release Information:</strong></h2>
<a href="http://open-estuary.com/estuary-download" target="_blank"><u>Please click here to go to the download page of this release</u></a>
<pre>Release Version         : v2.3
Release Date            : 14-Nov-2016
Applications            : (For all supported distributions)
   Docker               : v1.6.2
   ODP                  : v1.2
   MySQL                : percona-5.6.22-72.0
   Armor tools          : include perf, gdb, strace... (totally more than 40 tools for system debug\analyse\diagnosis）
Distributions Supported : Ubuntu 15.04 vivid, Fedora 22, OpenSuse Trumbleweed, Debian 8.5.0, CentOS 7, RancherOS 0.4.3, MiniOS 1.1
Kernel Version          : 4.4.11 
Bootloader Info         : UEFI 2.3 + Grub 2.02-beta3
   Boot mode            : ESL, Flash(exclude D03), PXE, NFS, SATA, SAS, USB, USB CDROM
Boards Supported        : D02(ARM64), D03(ARM64), HiKey(ARM64), QEMU v2.2.0(VM on X86)
Deployment Methods      : Manual binaries, Auto USB disk, Auto ISO file, Auto PXE</pre>
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel /distribution versions/applications at the earliest.
<h2><strong>Changelog</strong>:</h2>
<pre>1. Supported D03 board with 50MHz crystal officially
2. Officially supported D02/D03 based on ACPI
3. Linux kernel version upgraded to v4.4.11 (based on Linaro RPB 16.06)
4. Greatly improved stability of D02 SAS disk (UUID, Grub loading)
5. Enabled KVM(ACPI+DTS) support for D02/D03
6. Firstly support BMC load ISO
7. Fixed most major issues found in rc0 &amp; rc1, include but not limited to: UEFI, USB speed, build, distribution, etc
8. Improved build script:
   * Split to multi modules
   * Support build instance
   * Add compatibility with v2.2 and previous build commands
9. Improved website functionalities:
   * Issue tracker anonymous login removed due to security issue
   * Binary download mirror for China to improve the speed of download for China Users
10. Enhanced Caliper functionalities
   * Automatic test report generation in excel and linking of the same in the report
   * Caliper automation script updates
   * Caliper Multi target support from single host
   * Caliper incremental build on multi targets
   * Caliper integration on Jenkins
   * Report re-organization and formatting
11. Improved mini-rootfs to support full functional ssh server/client
12. Enabled LAMP based on docker officially
13. Updated documentation on project and website</pre>
<h2><b>Known issues</b>:</h2>
<pre>1. ARM ACPI not fully supported(e.g. ESL/NOR Flash booting, earlycon)
2. HiKey ACPI not supported</pre>
