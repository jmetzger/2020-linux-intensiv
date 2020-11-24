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

# Performance 

  * Reference: https://unix.stackexchange.com/questions/7122/does-lvm-impact-performance

```

LVM is designed in a way that keeps it from really getting in the way very much. From the userspace point of view, it looks like another layer of "virtual stuff" on top of the disk, and it seems natural to imagine that all of the I/O has to now pass through this before it gets to or from the real hardware.

But it's not like that. The kernel already needs to have a mapping (or several layers of mapping actually) which connects high level operations like "write this to a file" to the device drivers which in turn connect to actual blocks on disk.

When LVM is in use, that lookup is changed, but that's all. (Since it has to happen anyway, doing it a bit differently is a negligible performance hit.) When it comes to actually writing the file, the bits take as direct a path to the physical media as they would otherwise.


```

