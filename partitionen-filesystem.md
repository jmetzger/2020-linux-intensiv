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

```
