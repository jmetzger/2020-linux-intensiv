# Tipps & Tricks 

## RDP-Verbindung statt über VPN über SSH herstellen 

```
# -p port 
# -l user
# -N do not execute remote commands 
ssh -L 5000:192.168.178.26:3389 LINUXSERVER -p 22500 -l LINUXUSER -N 
# Dann aufruf von rdp -> localhost:5000 
```

## Reverse Forwarding 

```
Specifies that connections to the given TCP port or Unix
socket on the remote (server) host are to be forwarded to
the local side.
# Es es nicht notwendig port-forwarding dafür auf dem Router zu machen 
ssh -R 80:localhost:80 user@remoteserver 
```

## letzten Befehl als sudo ausführen (aus history) 

  * sudo !! 
  
## Verzeichnisstruktur als Baum anzeigen 

```
# unter Ubuntu installieren 
apt install tree

tree /home/centos01 

```
