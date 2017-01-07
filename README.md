Linux I/O Profiler (ioprof)
===========================

The Linux I/O profiler (ioprof) is a tool that provides significant insight into I/O workloads
while remaining easy to use.  It reports the following information:

* I/O Histogram   - Great for determining size of hot data for SSD caching
* I/O Heatmap     - Useful visualization to "see" where the hot data resides
* I/O Size Stats  - IOPS and bandwidth stats, which is useful for mixed workloads
* Top Files (opt) - Can ID top accessed files in EXT3/EXT4 filesystems
* Zipf Theta      - An estimate of Zipfian distribution theta

The tool is recommended to be used to further analyze I/O intensive workloads after running tools like iostat, since blktrace/blkparse can affect performance.

It is intended to be stable enough to use to profile production systems and makes every
attempt to minimize resource utilization.  In additon, the trace file is self-contained
and can be offloaded for analysis on a separate system.

Contents
========

* README    - This file
* LICENSE   - GPLv2 license
* ioprof.pl - The script

Dependencies
============
Perl v5.x and Perl Core Library

Requires the following tools:
* fdisk
* blktrace
* blkparse

Optional PDF report requires:
* gnuplot
* pdf2latex
* terminal pngcairo

Design
======
The tool currently groups statistics into 1MB "buckets" to provide relatively
accurate results, while minimizing system resources.

TODO:
=====
* Confirm XFS filesystem tracing
* Add option to specifiy output file name
* Add option to specify temp directory
* Improve file mapping performance

Maintainers
===========
Benjamin Donie <benjamin.j.donie@intel.com>
