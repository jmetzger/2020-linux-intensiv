## Sudo 

### Konfiguration 

```
Erfolgt in /etc/sudoers
/etc/sudoers.d/ (Verzeichnis) 

Entscheidend eine Zeile die mit % für Gruppe beginnt,
z.B. mit passwort-eingabe des ausführenden Benutzers.

Beispiel: Benutzer wäre training t
training@foo$ sudo su - # Hier muss dann das Passwort von training eingegeben werden 

# Allow members of group sudo to execute any command
%sudo	ALL=(ALL:ALL) ALL
# Nutzer training muss der Gruppe sudo angehören 

```

### Konfigurations-Beispiel für Nobleprog 

```
root@jochen-g14d:/etc/sudoers.d# cat nobleprog 
nobleprog ALL=(ALL:ALL) NOPASSWD:ALL
```

### Sudo - User anlegen (root) 

```
apropos user # find command adduser 
sudo adduser training 
# is group sudo present on system 
cat /etc/group | grep sudo
man usermod # Supplementary Groups

# Add user training to supplementary group
usermod -aG sudo training 

# Testing 
su - training # change to user 
sudo su - # find out if user training can execute sudo commands 
```

### Einen Nutzer zum sudo nutzer machen 

```
# auf Debian / Ubuntu 
# ist sudo also sudo - Gruppe definiert, die alles darf, was root darf
usermod -aG sudo dein_benutzer 

# auf Centos 
usermod -aG wheel dein_benutzer 
```
