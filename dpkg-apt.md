# dpkg / apt 

## Show all files/directories being installed by package 

  * Important: without files being created by install-script 
  
```
dpkg -L openssh-server 
```

## dpkg -l - show all packages 

```
dpkg -l 
```

## update repo & update system 
```
apt update 
apt upgrade 
apt dist-upgrade
```

## autoremove ## 
```
apt autoremove 
```

## reinstall config - files 

```
apt-cache pkgnames pulse |xargs -n 1 apt-get -o Dpkg::Options::="--force-confmiss" install --reinstall
```

## deinstallation 

```
apt remove package  # leave config-files 
apt purge package # also delete config files
```
