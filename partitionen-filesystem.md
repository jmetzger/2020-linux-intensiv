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

## Resize (bigger) ext 4 

```
# enhance partition
parted /dev/sdb1 
# resizepart 
# number+ new size 
# quit 
udevadm settle
resize2fs /dev/sdb1 

```

## Shrink (smaller) ext4 
```
# shrink partion 
# size should smaller
resize2fs /dev/sdb1 4G 
# shrink partition to new size 
parted
# resizepart 
# 1
# new reduced size 
# quit 
# eventually adjust to real size 
#of partition
resize2fs /dev/sdb1 
```

## Create partion with xfs 
```
parted /dev/sdb
# create partition 
mkpart 
# 2
# name - e.g. test
# filesystem: xfs 
# start: 
# end: 
# quit 
udevadm settle
# on ubuntu install xfs 
apt install xfsprogs 
mkfs.xfs /dev/sdb2
# mount 
mkdir /mnt/platte3
mount /dev/sdb2 /mnt /mnt/platte 
```

## Resize (increase) xfs 
```
parted /dev/sdb
# increase partition
# resizepart 
# number: 2
# size: 6GB 
# quit 
udevadm settle 
xfs_growfs /dev/sdb2 
```

## Backup and restore xfs

```
 sdb
├─sdb1     ext4              ef2cc434-236f-4654-b773-72c7a61fe447   /mnt/platte
└─sdb2     xfs               9fc967e0-eee0-4cf4-9fc8-fcb9cf1a037f   /mnt/platte3
 
 xfsdump -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3
 xfsrestore -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3

```

## Shrink xfs 

```
# Step 1: dump partition 
xfsdump -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3
# Step 2: partition mit parted verkleinert 
#parted /dev/sdb  
#resizepart 
#1
#4GB
# quit
udevadm settle
mkfs.xfs -f /dev/sdb2
xfsrestore -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3
```

