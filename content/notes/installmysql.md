+++
title = "MySQL Low Memory Gotcha"
weight = 0
date = 2017-07-30T18:10:02-04:00

showChildren = true

[menu.main]
	Name = "MySQL Low Memory Gotcha"
	parent = "Notes"
+++

When installing MySQL Client/Server on Ubuntu, if the system has low memory
(< 1GB including swap), the installation can silently fail and MySQL Server will
never sucessfully start.

This can be remedied by adding (or increasing) the size of swap.

--------

Check Swap Information
----------------------

The following command will print swap info as seen below.
```
$ sudo swapon --show
```

This shows that there is a 2G swapfile on the system. If there is no swapfile
one should be created to fix this issue as well as for general system
responsiveness.
```
NAME		TYPE	SIZE	USED	PRIO
/swapfile	file	2G		195.6M	-1
```

Create a Swap File
------------------

Allocate a new 2G file to use as a swap with the proper permissions.
```
$ sudo fallocate -l 2G /swapfile
$ sudo chmod 600 /swapfile
```

Enable the swap file
```
$ sudo mkswap /swapfile
$ sudo swapon /swapfile
```

Make the Swap File Permanent
----------------------------
Add the following line to the bottom of your `/etc/fstab` (or file systems table)
```
/swapfile	none	swap	sw	0	0
```

This page is based on [this DigitalOcean Article](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04). Please see this link for much more
information about swaps in general.