# Systemd 

```
systemctl status sshd 
# Rausfinden welche aktivierten / laufenden Dienste 
systemctl list-units -t service 
# Rausfinde welche überhaupt 
systemctl list-unit-files -t service 

# default target anzeigen 
# in welches target wird gebootet 
systemctl get-default 
systemctl set-default multi-user 

# see configuration of units 
systemctl cat multi-user.target 
systemctl cat sshd.service # centos 

```
