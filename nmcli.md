# nmcli 

# object connection (most important) 

```
# show all connections 
nmcli conn show 
# show a specific connect
nmcli conn show enp0s3 
# show a specific parameter 
nmcli -g connection.id conn show enp0s3
# create a static connection 
nmcli con add con-name static1 ifname enp0s3  type ethernet \
  ip4 192.168.100.100/24 gw4 192.168.100.1
# enable connection 
nmcli con up static1 
# modifiy connection 
nmcli con mod static1 ipv4.dns "8.8.8.8 8.8.4.4"
```
