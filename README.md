# Lab 2.1 cgroups

The first thing is to install `cgroup-tools`. This package is a collection of command-line utilities for managing and interacting with Linux control groups or `cgroups`.
```bash
$ sudo apt update
$ sudo apt install -y cgroup-tools
```
To test things are working we can run a command like `lscgroup` which lists all the current `cgroups` configured on the system. The output is in the format
```bash
controler:path
```
Where the cgroup controller, or subsystem, is before the colon, e.g., cpu, memory, and the path in the cgroup hierarchy after the colon. We can also list cgroups by process ID or PID. For example:
```bash
$ sudo cat /proc/1/cgroup
```
This lists the cgroups associated with processes with PID 1, or the first process started at boot.
```bash
bernie@ubuntu:~$ sudo cat /proc/1/cgroup
13:memory:/init.scope
12:devices:/init.scope
11:freezer:/
10:cpuset:/
9:rdma:/
8:perf_event:/
7:pids:/init.scope
6:cpu,cpuacct:/init.scope
5:blkio:/init.scope
4:hugetlb:/
3:misc:/
2:net_cls,net_prio:/
1:name=systemd:/init.scope
0::/init.scope
```
