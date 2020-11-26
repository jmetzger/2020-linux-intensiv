# Questions 

## How to boot/setup raid-1 // software raid with linux 

  * https://serverfault.com/questions/634482/setting-up-a-bootable-multi-device-raid-1-using-linux-software-raid
  
## How to update only kernel on centos 8 

  * dnf upgrade kernel 
  * be sure to reboot, that new kernel is loaded 
  
## Why do bluetooth devices not work within lxc containers ? 

  * Kernel as of 2017 does not support bluetooth namespaces 
  * namespacing bluetooth devices 
  * https://github.com/lxc/lxd/issues/3265
  
## How is Ubuntu Live Patch working 

  * Module with patches is compiled with patches
  * modules is loaded and functions are redirected with ftrace 
  * https://ruffell.nz/programming/writeups/2020/04/20/everything-you-wanted-to-know-about-kernel-livepatch-in-ubuntu.html

## Is docker based on lxc ? 

  * Yes ! 
  * ... since it is based on LXC
  * https://www.upguard.com/blog/docker-vs-lxc#:~:text=Docker%20is%20developed%20in%20the,provided%20by%20the%20underlying%20infrastructure.
 
```
Docker is developed in the Go language and utilizes LXC, cgroups, and the Linux kernel itself. Since it's based on LXC, a Docker container does not include a separate operating system; instead it relies on the operating system's own functionality as provided by the underlying infrastructure.22.10.2020
```

## What is /var/log/hp on Ubuntu ?

```
# this is created and used by hplip (Hewlett Packard Image Printing) 
# and is installed by default 
dpkg -L hplip 
...
...
/var/log/hp
...
```

  
  
