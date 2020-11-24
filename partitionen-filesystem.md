# Partitionen und Filesysteme anlegen / ändern 

## Schritt 1 (virtualbox) system herunterfahren 

```
# not possible to add harddisk when system is running (virtualbox)

# Change - on machine in GUI of virtualbox 
# Add new harddisk 
```

## Parted 

```
# open interactively 
parted 
# 
help
# show specific help of command
help mkpart 

select /dev/sdb 
print 
unit MiB # change unit 
print 

# create partition table 
mklabel gpt 

mkpart 
# create partition:
# name: data 
# type: ext4 
# start: 2048s 
# end: 5GB 

quit
```

## Mount partition 

```
mkdir /mnt/platte
mount /dev/sdb1 /mnt/platte 

# problem device busy 
cd /mnt/platte
umount /dev/sdb1 
# --> not working device busy
# -- because you or another user is in partition 
lsof /mnt/platte 
# eventually kill other process
```

## Mount persistently 
```
# for testing: be sure, partition not is not mounted 
mount /mnt/platte 
# adjusted /etc/fstab // add entry ad end of line  
 tail /etc/fstab
/dev/sdb1                 /mnt/platte             ext4    defaults        0 0
# testing -v - verbose -a  ist für everything from /etc/fstab
# be careful, if we have an error here, system will not reboot! 
mount -av 
```

