---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Caliper-for-Benchmarking
---

# 1 What is Caliper?

Caliper is a benchmarking framework for hardware platforms, integrated with industry standard tools and test cases. It provides detailed performance assessments for server platforms based on ARM64 and X86_64.

Caliper executes on a host system which is connected to the target platforms through network. The performance parameters are captured from the targets and converted to score through series of formulas. Thereby caliper intuitively presents various performance values and shows the performance gaps of the hardware platforms.

The uniqueness of caliper is a consolidated score based evaluation. The best performance in each test will get a score of 100. All other test scores are calculated relative to this. This provides a clear relative positioning of each target platform. It enables easy analysis of the performance levels and bottlenecks.

As the performance testing can depends on system hardware resources at the time of execution, it is bound to vary over repeated testing. In general, this makes it difficult to analyze the performance results. Caliper tries to solve by executing multiple iterations of each test on every platform and ensure low variance. This provides a more believable and stable scores throughout the report.

# 2 Caliper Setup

![https://raw.githubusercontent.com/open-estuary/open-estuary.github.io/master/img/caliper_setup1.png](https://raw.githubusercontent.com/open-estuary/open-estuary.github.io/master/img/caliper_setup1.png)

Caliper requires:

*   Two network switches - one for 1G network connection and another for 10G network connection.
*   Target platform on which all test tools will be execute.
*   Two machines which acts as clients.
*   One machine for caliper host.
*   Extra client (connected through eth3) for specific test cases where target to be stressed with multiple network interfaces.

# 3 Caliper Configuration

This section will discuss about the high level steps involved for caliper configurations.

Please see the detailed steps from the manual in the following link:

[https://github.com/open-estuary/caliper/blob/master/docs/Caliper_User_Manual.pdf](https://github.com/open-estuary/caliper/blob/master/docs/Caliper_User_Manual.pdf)

Get the caliper tool from [https://github.com/open-estuary/caliper.git](https://github.com/open-estuary/caliper.git)

Install the caliper in your system using below steps:

*   Install the dependency packages for all the machines to execute tools.
*   Configure system login information in ~/caliper_output/configuration/config/client_config.cfg file.
*   Choose the tools which user wants to execute from ~/caliper_output/configuration/test_cases_cfg/ directory.

# 4 Caliper Execution

Executes the caliper with "caliper -brps" command. By default caliper command is configured with "brps" option.

To execute caliper with the supported options, refer caliper user manual section 5.1.

# 5 Generate caliper report in HTML format

Refer section 5.2 in the user manual. High level steps are as follows:

*   After the successful caliper execution, it generated three files form each platform (platform.yaml, platform_score.yaml, platform_hw_info.yaml) inside the ~/caliper_output/&lt;workspace directory&gt;/output/results/yaml directory.
*   Copy these files into ~/caliper_output/frontend/frontend/data_files/Input_Logs/ directory as specified in caliper user manual.
*   Execute "caliper -BRPSw" command.
*   Report will be generated as ~/caliper_output/&lt;_WS_current_data_time&gt;/output/results/test_results.tar.gz.
*   Untar the test_results.tar.gz file and open index.html file with google chrome explorer.

# 6 General Tips

## 6.1 Checklist for caliper execution

*   Confirm the hostname configuration in below files for hadoop tool execution:

In /etc/hostname file:
localhost.localdomain

In /etc/hosts add this line:
127.0.0.1 localhost

*   After updating above files, user has to reboot the target platform.
*   Mount separate disk (Example: /dev/sdb1) at /mnt/sdb (create the mount if not exists) for storage tools testing.
*   Start mysql server for centos target platform: cd /usr/local/mysql; ./bin/mysqld_safe &amp;
*   Check all Ethernet interfaces which will be use for caliper execution.
Use this command to check the Ethernet interfaces: ethtool &lt;interface name&gt;

*   Check the ping response of all the ip addresses which will be use for caliper execution. (Refer ~/caliper_output/configuration/config/client_config.cfg file for ip addresses which will be used for caliper execution)

## 6.2 Caliper output log verification

After caliper execution has been completed, verify below files are present in the workspace.

*   output/final_parsing_logs.yaml – This file will be used for caliper framework. It is an intermediate file, which is not relevant for end user.
*   output/results_summary.log – summary information of tool execution status.
*   output/caliper_exe.log – execution time of tool
*   caliper_build/&lt;each tool build log&gt; - If the tool is successfully build, then the file name will be &lt;tool_name_arch_name&gt;.suc. If the tool in not able to build successfully, then the file name will be &lt;tool_name_arch_name&gt;.fail. User has to review the reason for failure and fix the issue.
*   caliper_exec/&lt;each tool output log&gt; - The output log of each tool will be present in caliper_exec directory. If tool execution has been failed, then user can review the log file and fix the issue accordingly.
*   result/yaml/&lt;platform name given in client_config.cfg file&gt;.yaml – This file contain the test case results of each tool.
*   results/yaml/&lt;platform name given in client_config.cfg file&gt;_score.yaml – This file contain the test case results of each tool in compressed way.
*   results/yaml/&lt;platform name given in client_config.cfg file&gt;_hw_info.yaml – This file contain the hardware information of the platform.

## 6.3 Caliper re-execution for failed tools

Refer below steps if user wants to execute caliper for those tools which has been failed.

*   Execute this command: cd ~/caliper_output/&lt;workspace created by caliper&gt;/test_cases_cfg/
*   Choose only failed tools in following files:

common_cases_def.cfg

server_cases_def.cfg

application_cases_def.cfg

*   Execute this command: caliper -brpsf &lt;workspace created by caliper&gt;
*   After successful execution of all the tools, uncomment all the tools in common_cases_def.cfg, server_cases_def.cfg and application_cases_def.cfg files.
*   Perform parsing and scoring using the command: caliper -BRpsf &lt;workspace created by caliper&gt;
*   Please verify that all the yaml files has been created in “output/results/yaml” directory.

## 6.4 Change platform name in HTML report

If user wants to change the name of the platform in caliper HTML report, then make following changes:

*   Execute this command: cd ~/caliper_output/frontend/frontend/data_files/Input_Logs/
*   Update the “platform_name&gt;.yaml” files in Input_Consolidated directory and change the name inside this file at 2 places: (see highlighted text)

Configuration:

Byte_order: Little Endian

CPU: '64'

CPU_type: '*TBA'

Hostname: <span style="color: #993300;">platform_name</span>

L1d_cache: 1024 kB

L1i_cache: 1536 kB

L2_cache: 8192 kB

L3_cache: 32768 kB

Machine_arch: aarch64

Memory: 523535MB

OS_Version: Linux 4.9.20+

name: <span style="color: #993300;">platform_name</span>

*   Follow same procedure for &lt;<span style="color: #993300;">platform_name</span>&gt;_score.yaml files in Input_Report directory.
*   Update the name of &lt;<span style="color: #993300;">platform_name</span>&gt;_hw_info.yaml files in Input_Hardware directory.
*   Execute command: caliper -BRPSw
*   New workspace will be created in ~/caliper_output directory.
*   Switch to the new workspace and extract test_results.tar.gz file in output/results directory.
*   Open index.html web page.

# 7 Appendix

Caliper user manual: [https://github.com/open-estuary/caliper/blob/master/docs/Caliper_User_Manual.pdf](https://github.com/open-estuary/caliper/blob/master/docs/Caliper_User_Manual.pdf)

Caliper developer manual: [https://github.com/open-estuary/caliper/blob/master/docs/Caliper_Developer_Manual.pdf](https://github.com/open-estuary/caliper/blob/master/docs/Caliper_Developer_Manual.pdf)

Nginx tool user guide: [https://github.com/open-estuary/caliper/blob/master/docs/Nginx_Tool_User_Guide.pdf](https://github.com/open-estuary/caliper/blob/master/docs/Nginx_Tool_User_Guide.pdf)

Redis tool user guide: [https://github.com/open-estuary/caliper/blob/master/docs/Redis_Tool_User_Guide.pdf](https://github.com/open-estuary/caliper/blob/master/docs/Redis_Tool_User_Guide.pdf)

# 8 List of Benchmarks Supported in Caliper

<table style="height: 1589px;" border="0" width="1317" cellspacing="0"><colgroup width="85"></colgroup> <colgroup width="454"></colgroup>
<tbody>
<tr>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">1</span></td>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">openssl</span></td>
<td align="left">https://www.openssl.org/</td>
</tr>
<tr>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">2</span></td>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">coremark</span></td>
<td align="left">EEMBC, https://www.eembc.org/</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">3</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">linpack</span></td>
<td align="left">[http://www.netlib.org/linpack/](http://www.netlib.org/linpack/)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">4</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">nbench</span></td>
<td align="left">[http://www.tux.org/~mayer/linux/bmark.html](http://www.tux.org/~mayer/linux/bmark.html)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">5</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">lmbench</span></td>
<td align="left">[http://www.bitmover.com/lmbench/](http://www.bitmover.com/lmbench/)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">6</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">cachebench</span></td>
<td align="left">[http://icl.cs.utk.edu/projects/llcbench/cachebench.html](http://icl.cs.utk.edu/projects/llcbench/cachebench.html)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">7</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">iozone</span></td>
<td align="left">[http://www.iozone.org/](http://www.iozone.org/)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">8</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">openblas</span></td>
<td align="left">[https://github.com/xianyi/OpenBLAS.git](https://github.com/xianyi/OpenBLAS.git)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">9</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">netperf</span></td>
<td align="left">[http://www.netperf.org/netperf/](http://www.netperf.org/netperf/)</td>
</tr>
<tr>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">10</span></td>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">dhrystone</span></td>
<td align="left">http://fossies.org/linux/privat/old/dhrystone-2.1.tar.gz/</td>
</tr>
<tr>
<td align="left" height="18">11</td>
<td align="left" height="18"> qperf</td>
<td align="left">install qperf - "apt-get install qperf" or "yum install qperf"</td>
</tr>
<tr>
<td align="left" height="18">12</td>
<td align="left" height="18"> nginx</td>
<td align="left">[http://nginx.org/download/nginx-1.11.13.tar.gz](http://nginx.org/download/nginx-1.11.13.tar.gz)</td>
</tr>
<tr>
<td align="left" height="18">13</td>
<td align="left" height="18"> redis</td>
<td align="left">[https://github.com/sjtuhjh/applications](https://github.com/sjtuhjh/applications)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">14</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">fio</span></td>
<td align="left">GPL v2, [https://github.com/axboe/fio/blob/master/COPYING](https://github.com/axboe/fio/blob/master/COPYING)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">15</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">hibench</span></td>
<td align="left">[https://github.com/intel-hadoop/HiBench](https://github.com/intel-hadoop/HiBench)</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">16</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">iperf3</span></td>
<td align="left">BSD license, [http://iperf.sourceforge.net/ ,https://github.com/esnet/iperf](http://iperf.sourceforge.net/)</td>
</tr>
<tr>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">17</span></td>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">netperf</span></td>
<td align="left">HP license, http://www.calculate-linux.org/packages/licenses/netperf</td>
</tr>
<tr>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">18</span></td>
<td align="left" height="17"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">scimark2</span></td>
<td align="left">public domain, http://math.nist.gov/scimark2/credits.html</td>
</tr>
<tr>
<td align="left" height="34"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">19</span></td>
<td align="left" height="34"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">sysbench</span></td>
<td align="left">GPL v2, [https://github.com/akopytov/sysbench , http://imysql.com/wp-content/uploads/2014/10/sysbench-manual.pdf](https://github.com/akopytov/sysbench)</td>
</tr>
<tr>
<td align="left" height="18">20</td>
<td align="left" height="18"> unixbench</td>
<td align="left">https://github.com/kdlucas/byte-unixbench</td>
</tr>
<tr>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">21</span></td>
<td align="left" height="18"><span style="font-family: 'Liberation Mono', 'Cumberland AMT', Cumberland, 'Courier New', Cousine, 'Nimbus Mono L', 'DejaVu Sans Mono', Courier, 'Lucida Sans Typewriter', 'Lucida Typewriter', Monaco, Monospaced;">stress-ng</span></td>
<td align="left">http://kernel.ubuntu.com/~cking/stress-ng/</td>
</tr>
<tr>
<td align="left" height="18">22</td>
<td align="left" height="18">Unzip</td>
<td align="left">Compression benchmark</td>
</tr>
<tr>
<td align="left" height="17">23</td>
<td align="left" height="17">Compile</td>
<td align="left">Compilation performance benchmark</td>
</tr>
</tbody>
</table>
Suggestions/ feedbacks @ shyju.pv@gmail.com
