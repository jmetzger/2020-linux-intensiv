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



  
  
