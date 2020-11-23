# Kernel Parameter 

## Während der Laufzeit 

```
root@ubuntu01:/proc/sys/net/ipv4# echo ip_forward
ip_forward
root@ubuntu01:/proc/sys/net/ipv4# cat ip_forward
0
# Ab sofort Pakete, die du bekommst, lieber kernel, weiterleiten
root@ubuntu01:/proc/sys/net/ipv4# echo 1 > ip_forward
root@ubuntu01:/proc/sys/net/ipv4#


```
