# rpm/dnf/yum 

## Find all files that are installed by none installed package

```
rpm -qlp telnet-server-1.2-137.1.i586.rpm
```

## rpm -commands 

```

  147  rpm -qa # show all packages
  148  rpm -qa | grep ssh # show ssh package
  149  rpm -ql openssh-server# list content 
```

## uninstall software 

```
yum remove vim 
# better
dnf remove vim 

```

## which package installs specific program 

```
# which package provides mysql client 
dnf provides mysql 
```

## update of system 

```
# also reads new versions from repo 
yum update 
```

## reinstall configuration files 

  * https://linuxfreelancer.com/restore-original-files-from-rpm-package
  
```
# uninstall 

# reinstall with force 
rpm -ivh --force packagename.rpm
```
rpm -ivh --force packagename.rpm
