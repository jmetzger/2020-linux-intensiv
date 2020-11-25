# timedatectl und locales

## Sprache setzen
```
# current state 
localectl 
localectl set-locale en_US 
localectl list-locales 
```

## Alles was mit Zeit zu tun hat.

```
timedatectl 
```

## Welcher NTP-Dienst läuft für die Zeit 

```
# Centos 
chronyd
systemctl status chronyd.service 
chronyc sourcestats

# Ubuntu - verwendet timesyncd 
systemctl status systemd-timesyncd.service 
timedatectl timesync-status 

## ntpd wird bei beiden nicht verwendet für systemd 
```

