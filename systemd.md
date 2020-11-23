# Systemd 

```
systemctl status sshd 
# Rausfinden welche aktivierten / laufenden Dienste 
systemctl list-units -t service 
# Rausfinde welche überhaupt 
systemctl list-unit-files -t service 

# Alle targets anzeigen 
systemctl list-unit-files -t target  

# is target aufrufbar ? 
systemctl cat mutli-user.target | grep AllowIsolate  # should be in last line 

# default target anzeigen 
# in welches target wird gebootet 
systemctl get-default 
systemctl set-default multi-user 

# see configuration of units 
systemctl cat multi-user.target 
systemctl cat sshd.service # centos 

```
