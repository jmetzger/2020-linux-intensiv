# Systemd 

## systemctl 

```
systemctl status sshd 
# Rausfinden welche aktivierten / laufenden Dienste 
systemctl list-units -t service 
# Rausfinde welche überhaupt 
systemctl list-unit-files -t service 

# Alle targets anzeigen 
systemctl list-unit-files -t target  

# is target aufrufbar ? 
systemctl cat multi-user.target | grep AllowIsolate  # should be in last line 

# default target anzeigen 
# in welches target wird gebootet 
systemctl get-default 
systemctl set-default multi-user 

# see configuration of units 
systemctl cat multi-user.target 
systemctl cat sshd.service # centos 

```

## tmpfiles.d 

  * Create manage temporary files 
  
```
# just to have an idea how it works 
cp -a /usr/lib/tmpfiles.d/tmp.conf /etc/tmpfiles.d/tmp.conf 

# Edit file, that it has the following content 
d /tmp/test 1777 root root -

# Get in / - directory, to see that is works everywhere 
cd /

# Execute manually to check, if it works 
systemd-tmpfiles --create 

# check if dir exits
ls -la /tmp/test 

# Hint: Deleting and setup is done daily and on boot 
# by the following services and timers:
# systemctl list-unit-files | grep tmpfiles
systemd-tmpfiles-clean.service             static          enabled
systemd-tmpfiles-setup-dev.service         static          enabled
systemd-tmpfiles-setup.service             static          enabled
systemd-tmpfiles-clean.timer               static          enabled
```
