# Systemd 

## layers of systemd 

```
/lib/systemd/system  # never touch this is admin 
/etc/systemd/system
/run/systemd/system 
```

## how it is started

```
units:

Innerhalb eines Targets , ausführen von

- service(s)
- mount(s)
- socket(s) 
- timer (s)

Oder/und
     (sub)target(s) 
        service
        mount
        timer
        socket
```

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

# show running and next scheduled timers 
systemctl list-timers 

```

## Dienste starten/aktivieren/deaktivieren/überprüfen 

```
systemctl start httpd 
systemctl start apache2 

systemctl status apache2 
systemctl status httpd 

systemctl enable apache2
systemctl enable httpd

systemctl disable apache2
systemctl disable httpd

systemctl is-enabled apache2
systemctl is-enabled httpd 
# wichtig wenn enabled rückgabe wert 0
echo $? 
0
# wenn nicht aktiviert 
echo $? 
1 
```

## System runterfahren 

```
# system runterfahren und ausschalten 
systemctl poweroff 
poweroff 
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

## timers ## 

```
systemctl list-timers 
```

## journalctl ##

```
# show events of a specific unit 
journalctl -u sshd.service 
```

## Example debugging of timer event 

```
systemctl list-timers  | head -n 3
NEXT                         LEFT       LAST                         PASSED       UNIT                         ACTIVATES
Mon 2020-11-23 13:11:17 CET  44min left Mon 2020-11-23 12:11:16 CET  15min ago    dnf-makecache.timer          dnf-makecache.service
Tue 2020-11-24 00:00:00 CET  11h left   Mon 2020-11-23 09:28:30 CET  2h 57min ago unbound-anchor.timer         unbound-anchor.service
[root@trn01 tmp]# journalctl -u dnf-makecache.service 
```

