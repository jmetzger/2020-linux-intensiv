# Nmap - Timer

## Walkthrough 

```
# Schritt 1:
# /usr/local/sbin/scan.sh
[root@centos8-01 sbin]# cat scan.sh
#!/bin/bash
IP_RANGE=192.168.56.100-103
nmap -A -T4 $IP_RANGE

# Schritt 2: service erstellen
# systemctl edit --force --full scan.service 
# /etc/systemd/system/scan.service
[Unit]
Description=nmap scanning of environment

[Service]
Type=oneshot
ExecStart=/usr/local/sbin/scan.sh
#RemainAfterExit=true
StandardOutput=journal

## nach dem Speichern kann man das bereits testen mit 
# systemctl start scan.service 
## Ergebnis im Journal 
# journalctl -u scan.service 

# Schritt 3: 
# Timer angelegt :
# systemctl edit --force --full scan.timer 
# /etc/systemd/system/scan.timer
[Unit]
Description=Timer for Scan Service

[Timer]
OnCalendar=*:0/5

[Install]
WantedBy=basic.target

# Schritt 4:
# Timer starten und aktivieren
systemctl enable scan.timer 
systemctl start scan.timer 

# Schritt 5:
# Beobachten und glücklich sein 
systemctl list-timers 
# <- taucht der Timer dort auf 

# Schritt 6:
# Reboot 
# und Danch : taucht der timer auf ? 
systemctl list-timers 
```
