# unattended-upgrades 

  * Automatic security updates in enabled by default on Ubuntu 20.04 LTS 
  * File 1 
```
# That's default on Ubuntu 20.04 
/etc/apt/apt.conf.d/20autoupgrades 
APT::Periodic::Update-Package-Lists "1";
APT::Periodic::Unattended-Upgrade "1";
```

  * File 2
```
/etc/apt/apt.conf.d/50unattended-upgrades 
# set needed configs here 


```
