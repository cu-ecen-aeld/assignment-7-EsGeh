# Assignment 7-2 - Building Kernel Drivers using buildroot (/ Yocto)

This Repository contains example kernel modules from the Linux Device Drivers 3 (http://lwn.net/Kernel/LDD3/) book.
This repository is used by the [assignment5](https://github.com/cu-ecen-aeld/assignment-5-EsGeh) repository, which builds and runs these modules using buildroot.
The [assignment3](https://github.com/cu-ecen-aeld/assignments-3-and-later-EsGeh/blob/main/assignments/assignment7/faulty-oops.md) repository contains an explanation how to debug faulty kernel modules (=> `assignments/assignment7/`).


ldd3: Linux Device Drivers 3 examples updated to work with recent kernels

# About
-----

Linux Device Drivers 3 (http://lwn.net/Kernel/LDD3/) book is now a few years
old and most of the example drivers do not compile in recent kernels.

This project aims to keep LDD3 example drivers up-to-date with recent kernels.

The original code can be found at: http://examples.oreilly.com/9780596005900/

# Compiling
----------

The example drivers should compile against latest Linus Torvalds kernel tree:
* git://git.kernel.org/pub/scm/linux/kernel/git/sfr/linux-next.git

To compile the drivers against a specific tree (for example Linus tree):
```
$ git clone git://github.com/martinezjavier/ldd3.git
$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
$ export KERNELDIR=/path/to/linux
$ cd ldd3
$ make
```

Bugs, comments or patches: See https://github.com/martinezjavier/ldd3/issues

# Latest Tested Kernel Builds
---------
The kernel builds below are the versions most recently tested/supported

* Ubuntu 18.04 kernel as of July 2020: 5.4.0-42-generic
* Ubuntu 20.04 kernel as of July 2021: 5.4.0-73-generic
* Yocto poky warrior branch kernel for qemu aarch64 builds: 5.0.19
* Yocto poky hardknott branch kernel for qemu aarch64 builds: 5.10.46
* Buildroot 2019.05 kernel for qemu builds: 4.9.16
* Buildroot 2021.02 kernel for qemu builds: 5.10
* Alpine 3.13 kernel as of May 2021: 5.10.29-lts, see [here](https://github.com/ericwq/gccIDE/wiki/ldd3-project) for detail.


# Eclipse Integration
---------4
Eclipse CDT integration is provided by symlinking the correct linux source directory with the ./linux_source_cdt symlink.
The .project and .cproject files were setup using instructions in [this link](https://wiki.eclipse.org/HowTo_use_the_CDT_to_navigate_Linux_kernel_source)
and assuming a symlink is setup in the local project directory to point to relevant kernel headers

This can be done on a system with kernel headers installed using:
```
ln -s /usr/src/linux-headers-`uname -r`/ linux_source_cdt
```
