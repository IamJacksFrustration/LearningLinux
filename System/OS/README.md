# Operating Systems
Diving into how a linux based operating system works. 

## Booting 
```
The BIOS controls the first part the boot process and provides the lowest level interface to peripheral devices. Written into read-only, permanent memory, it is always available for use.

Once loaded, the BIOS tests the system, looks for and checks peripherals, and then locates a valid device to boot the system. The BIOS then loads into memory whatever program is residing in the first sector of this device, called the Master Boot Record or MBR. 

The MBR is only 512 bytes in size and contains the boot loader (machine code instructions for booting the computer), along with the partition table. Once the BIOS finds and loads the boot loader into memory, it yields control of the boot process to it.*
```

## Kernel
Handling system calls is an important task for a kernel. Along with processes a user starts, there are typically many services that run in the background to enable things like internet connectivity. All of these taks are competing for the kernel's attention. 

# Userspace 
From what I can tell, using a linux shell gives a decent feel for what is happening under the hood. When you call a program like `cat` say, you know the actual binary might be somewhere else (like `/usr/bin/cat`). And yet, you can interact with the operating system to read a file by entering this command and providing a filename. 

This is an interaction in *userspace* and is only a tiny glimpse into what is actually happening for an operating system to run. The collection of functions like this are all actually interacting with the underlying kernel to every really get something done. This is because most useful operations, like interacting with filesystem say, requires making a system call. 

Moreover, all of the management of permissions, the allocation and management of memory and the loading and startup of the right firmware/drivers to connect to external devices like a monitor and keyboard are features created and handled by the kernel.


### Resources 
- [Boot Process](https://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-rg-en-4/s1-boot-init-shutdown-process.html)