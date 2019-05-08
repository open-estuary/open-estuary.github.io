<h2><strong>Release Information:</strong></h2>
<a href="http://open-estuary.com/estuary-download" target="_blank">Please click here to go to the download page of this release</a>
<pre>Release Version         : estuary-v2.0
Release Date            : 15-Sep-2015
Distributions Supported : Ubuntu 15.04 vivid, Fedora 22, OpenSuse Trumbleweed, Debian 8.2 Jessie
Kernel Version          : 4.1.6+
Bootloader Info         : UEFI + Grub 2.02
Boards Supported        : D01(ARM32), D02(ARM64), QEMU v2.2.0(VM on X86)</pre>
&nbsp;
<h2><strong>Introduction:</strong></h2>
Estuary is a development version of the whole software solution which target is the ICT market. It is a long term solution and focus on the combination of the high level components. It is expected to be re-based to top tip kernel / distribution versions / applications at the earliest.

&nbsp;
<h2>Changelog:</h2>
<pre>1. Upgrade kernel to v4.1.6
2. Enable Quick Start Deployment solution by USB disk.
3. Integrated latest drivers: PCIE, XGE, SAS.
4. Move all git repositories and documentations to new position.
    a. Repositories: https://github.com/open-estuary
    b. Website: http://www.open-estuary.com (IE11, Chrome 44, Firefox 40 are recommended.)
5. Validated &amp; supported more distributions: OpenSuse, Debian.
6. Improved Ubuntu distribution to be more stable.
7. Largely improved the efficiency of build.sh 
8. Enabled building grub from source code directly.
    Must mv grub.cfg file to root directory in boot partition on SATA.
9. Pubished the latest UEFI source code for D02 and enabled building UEFI from source code directly.
10. Upgraded Caliper project.
    a. Add compile, unzip, java scimark and ebizzy test cases.
    b. Add functional showing in the frontend, and fix some bugs
    c. Add crash handle part for target
    d. Add the feature to support the specified output directory and specified config files
11. Upgraded UEFI to add PCIE scanning.
    a. Remove GE4 and keep only GE5 on UEFI, to avoid confusion with 2 NICs.
    b. Re-enable PCI Express link up for port 1 and 2 (According to PCI Express slots on the board).
    c. Fix PXE timeout issue.
    d. Re-enable showbrdnum and setbrdnum commands on EBL.
    e. Fix several other bugs.
12. Move most documents into project directly, you can get them in build/&lt;platform&gt;/doc directory.</pre>
