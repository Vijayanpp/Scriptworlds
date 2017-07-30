---
layout: post_page
title:  Linux Internals
---


<p>Linux is a unix like operating system intended for computers (Intel x86 architectures). Linux operating system is first introduced on September 17, 1991 by Linus Torvalds. Linux operating system is initialy developed for computers, But now a days it is ported to to more platforms than any other operating system (ARM architecture). Android OS on smart phone is running with Linux based kernel. Linux has the largest installed base of all general-purpose operating systems. The development of Linux is one of the most prominent examples of free and open-source software collaboration. The underlying source code may be used, modified and distributed‍—‌commercially or non-commercially‍—‌by anyone under the terms of its respective licenses, such as the GNU General Public Licen</p>
<p>A Linux-based system is a modular Unix-like operating system, deriving much of its basic design from principles established in Unix during the 1970s and 1980s. Such a system uses a monolithic kernel, the Linux kernel, which handles process control, networking, access to the peripherals, and file systems. Device drivers are either integrated directly with the kernel, or added as modules that are loaded while the system is running.Separate projects that interface with the kernel provide much of the system's higher-level functionality. The GNU userland is an important part of most Linux-based systems, providing the most common implementation of the C library, a popular CLI shell, and many of the common Unix tools which carry out many basic operating system tasks. The graphical user interface (or GUI) used by most Linux systems is built on top of an implementation of the X Window System.
</p>
<h3>Design Over view of Linux</h3>
<p>The Linux OS is having two parts, Userspace mode and Kernel space mode, kernel space among classified into two context mode processor context and interrupt context mode. The details of user space mode and kernel space mode is as follows.
<p>
<p><b>Kernel mode:</b> Kernel is the hear of any operating system, which deals with operation of hardware on computer/target board. In Kernel mode, the executing code has complete and unrestricted access to the underlying hardware. It can execute any CPU instruction and reference any memory address. Kernel mode is generally reserved for the lowest-level, most trusted functions of the operating system. Crashes in kernel mode are catastrophic; they will halt the entire PC. This kernel code is executed in kernel space (dedicated memory for kernel, restricted to user space). Interrupt context mode and process context mode will come later sessions.
</p>
<p><b>User mode:</b> In User mode, the executing code has no ability to directly access hardware or reference memory. Code running in user mode must delegate to system APIs to access hardware or memory. Due to the protection afforded by this sort of isolation, crashes in user mode are always recoverable. Most of the code running on your computer will execute in user mode. User mode is executed in user space memory.
</p>

<h4>Installed components of a Linux system include the following;</h4>
<p>1. A boot loader, for example GNU GRUB, LILO, SYSLINUX, or Gummiboot. This is a program that loads the Linux kernel into the computer's main memory, by being executed by the computer when it is turned on and after the firmware initialization is performed.</p>
<p>2. An init program, such as the traditional sysvinit and the newer systemd, OpenRC and Upstart. This is the first process launched by the Linux kernel, and is at the root of the process tree: in other terms, all processes are launched through init. It starts processes such as system services and login prompts (whether graphical or in terminal mode).
</p>
<p>3. Software libraries, which contain code that can be used by running processes. On Linux systems using ELF-format executable files, the dynamic linker that manages use of dynamic libraries is known as ld-linux.so. If the system is set up for the user to compile software themselves, header files will also be included to describe the interface of installed libraries. Besides the most commonly used software library on Linux systems, the GNU C Library (glibc), there are numerous other libraries.</p>
<p>4. C standard library is the library needed to run standard C programs on a computer system, with the GNU C Library being the most commonly used. Several alternatives are available, such as the EGLIBC (which was used by Debian for some time) and uClibc (which was designed for uClinux).</p>
<p>5. Widget toolkits are the libraries used to build graphical user interfaces (GUIs) for software applications. Numerous widget toolkits are available, including GTK+ and Clutter developed by the GNOME project, Qt developed by the Qt Project and led by Digia, and Enlightenment Foundation Libraries (EFL) developed primarily by the Enlightenment team.</p>
<p>6. User interface programs such as command shells or windowing environments.</p>

<h3>FUNCTIONALITIES</h3>
 Following are functionalities of Linux kernel
* File management
* Memory management
* DMA support multimedia device
* Hardware access/control and interrupt handling using linux device drivers
* Power management support
* Schedule different task using scheduler
<p>It is important to know the design and development of linux device driver, And how it to port into target processor. Based on target, need to implement the device driver for communicating the user space app with the hardware. Coming class will give introduction on linux device drivers first.</p>
<p>Device driver in Linux platform for vendor specific device (Say we have accelerometer sensor from Analog semiconductor) on I2C/SPI interface, need two drivers for the proper working of that device. First one is the core device driver which configure the SOC(Application processor) registers and thus make read/write operation through I2C/SPI. Second one is the Vendor specific device driver which is purely dependent on the sensor part(Vendor) used. This device driver configures the interface specification between SOC and sensor, may configure registers of sensor device and vendor device driver calls SOC core device driver to send data over bus (I2C/SPI).</p>

<b>Prabhin CA</b>
