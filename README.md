<!----- Conversion time: 7.63 seconds.


Using this Markdown file:

1. Cut and paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β16
* Sat Mar 30 2019 10:52:06 GMT-0700 (PDT)
* Source doc: https://docs.google.com/open?id=179j5WrBL2yrSvJvUSekFPf9X5dXi9BrTff4ijlrK1lk
* This document has images: check for >>>>>  gd2md-html alert:  inline image link in generated source and store images to your server.

WARNING:
You have 6 H1 headings. You may want to use the "H1 -> H2" option to demote all headings by one level.

----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 3.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>



# Create Simple Container

Denis Rangulov

Total Virtualization

Innopolis University

2019


# Intro

The idea of the work is to create a process (own container), that is isolated, has its own namespaces, has its own root directory in file system, networking, can save its filesystem as file, and can even limit its own resources via CGroups. 

Then comparing the own container with LXC, Docker.


## How to run



*   Deploy own_container.c in some Linux OS on some machine (I used Ubuntu Linux 16.04 (64 bit) on [Microsoft Azure](https://cloud.mts.ru/) virtual machine)
*   Run commands:
    *   gcc own_container.c
    *   ./a.out
*   If you want to use CGroups to limit some resources, uncomment related lines in code and run commands before a program execution:
    *   sudo mkdir /sys/fs/cgroup/cpu/demo
    *   echo 50000 > /sys/fs/cgroup/cpu/demo/cpu.cfs_quota_us
    *   echo 100000 > /sys/fs/cgroup/cpu/demo/cpu.cfs_period_us


## Links

	This project on Github : \\\


# Tests

	To test my container against other products and host machine i have to measure <something> because <reasons, preferably with links to source>....

commands


<table>
  <tr>
   <td>Metric 
   </td>
   <td>Sysbench command
   </td>
   <td>Why this command
   </td>
   <td>What is interesting in sysbench output
   </td>
  </tr>
  <tr>
   <td>CPU total time [sec]
   </td>
   <td>sysbench --test=cpu --cpu-max-prime=20000 run
   </td>
   <td>I increase cpu-max-prime because i expect to see more noticable difference between total time in different containers. Considered to be a good example, found from the following ​ source<a href="https://www.howtoforge.com/how-to-benchmark-your-system-cpu-file-io-mysql-with-sysbench"> [SysBenchExample]</a>
   </td>
   <td>total time in secunds 
   </td>
  </tr>
  <tr>
   <td>File IO speed 
<p>
[Mb/sec]
   </td>
   <td>
<ul>

<li>sysbench --test=fileio --file-total-size=40G prepare

<li>sysbench --test=fileio --file-total-size=40G --file-test-mode=rndrw --init-rng=on --max-time=300 --max-requests=0 run

<li>sysbench --test=fileio --file-total-size=40G cleanup
</li>
</ul>
   </td>
   <td>File is 40 Gb size because otherwise, the system will use RAM for caching which tampers with the benchmark results
   </td>
   <td>Read,write speed
   </td>
  </tr>
</table>



# Table With Metrics


<table>
  <tr>
   <td>
   </td>
   <td>host machine
   </td>
   <td>my container
   </td>
   <td>LXC (Ubuntu 16 i386)
   </td>
   <td>Docker(Ubuntu 16)
   </td>
  </tr>
  <tr>
   <td>CPU  total time [sec]
   </td>
   <td>27.6424
   </td>
   <td>27.5593
   </td>
   <td>27.8297
   </td>
   <td>27.8827
   </td>
  </tr>
  <tr>
   <td>File IO speed
<p>
[Mb/sec]
   </td>
   <td>1.0885 
   </td>
   <td>1.1458
   </td>
   <td>1.1289
   </td>
   <td>1.1302
   </td>
  </tr>
</table>



# Some screens \
Host machine



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Create-Simple0.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Create-Simple0.png "image_tooltip")



## My container


# 

<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Create-Simple1.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Create-Simple1.png "image_tooltip")



## Docker(Ubuntu 16)



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/Create-Simple2.png). Store image on your image server and adjust path/filename if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/Create-Simple2.png "image_tooltip")



# Sources



1. [SysBenchExample] - "How to Benchmark Your System (CPU, File IO, MySQL) with Sysbench" \
[ https://www.howtoforge.com/how-to-benchmark-your-system-cpu-file-io-mysql-with-sysbench](https://www.howtoforge.com/how-to-benchmark-your-system-cpu-file-io-mysql-with-sysbench) 

<!-- Docs to Markdown version 1.0β16 -->
