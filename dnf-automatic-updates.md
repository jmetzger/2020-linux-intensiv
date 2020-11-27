# Automatic updates under Centos 8 / dnf 

## Walkthrough 

```
dnf install dnf-automatic
rpm -qi dnf-automatic # check if installed 
vi /etc/dnf/automatic.conf
# Commands
upgrade_type = security
# Emitters 
system_name = centos-8 # your hostname 
# message on every login 
emit_via = motd


# test manually 
dnf-automatic


systemctl enable --now dnf-automatic.timer
# eventually ? 
systemctl enable --now dnf-automatic-update.timer 
# 

# check 
systemctl list-timers *dnf-*

# login 
 /var/log/dnf.rpm.log
 


```


## References 

  * https://www.tecmint.com/dnf-automatic-install-security-updates-automatically-in-centos-8/
