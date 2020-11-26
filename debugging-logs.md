# Debugging logs 

```
Step1: 
systemctl status service-name 
# if step1 was not succesful 

Step2:
journalctl -u service-name 

# step 3: (if not step was not sucessful )
# Look in specific log files of service under 
/var/log 
e.g. mysql 
/var/log/mysql
e.g. mariadb
/var/log/mysql
or
/var/log/mariadb 

# if this does not work 
/var/log/messages or /var/log/syslog 

```
