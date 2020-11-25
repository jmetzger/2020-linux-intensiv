# xfsdump and xfsrestore 

## Backup and restore xfs

```
 sdb
├─sdb1     ext4              ef2cc434-236f-4654-b773-72c7a61fe447   /mnt/platte
└─sdb2     xfs               9fc967e0-eee0-4cf4-9fc8-fcb9cf1a037f   /mnt/platte3
 
 xfsdump -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3
 xfsrestore -f /mnt/platte/_mnt_platte3_2.xfsdump /mnt/platte3
```

## xfs inventar 

```
# Zeigt das Inventar an
# Bedeutet, was wurde bereits gesichert 
xfsdump -I 
```
