# LVM

# Step 1: Create lvm partitions 
```
parted
mkpart lvm1 2048s 2GB
mkpart lvm2 2GB 4GB
set 1 lvm on
set 2 lvm on 
quit

udedevadm settle

# ubuntu install lvm
apt install lvm2

# 
pvcreate /dev/sdb1
pvcreate /dev/sdb2 

# create physical volume group
vgcreate training1 /dev/sdb1

# create logical volume 
lvcreate -L 10MB -n mytrain training1 

```
