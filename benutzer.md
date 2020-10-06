## 6 Benutzer

### Wer bin ich (der eingeloggte Nutzer) ? 

```
# Wer bin ich / Unter welchem Benutzer bin ich eingeloggt  
whoami 
```

### Mehr über mich:

```
# Mehr über mich
id
```

### Alle Gruppen eines Benutzer anzeigen (in denen er Mitglied ist) 

```
groups 
```


### Benutzer ausgeben / anlegen 

```
# Location of users in system 
cat /etc/passwd 

man useradd
man adduser
# On Debian/Ubuntu 
# use adduser to interactively add a new user 
adduser training
# use useradd for scripts
# Important: Use options
useradd training 


```

### Unter einem anderen Benutzer anmelden (während einer Session)

```
su --login training
```

### Shell eines Benutzer ändern ###

```
# Direktes Ausloggen nach Login 
usermod -s /bin/false training
# Mit Ausgabe und Ausloggen nach Einloggen
usermod -s /usr/sbin/nologin training 
```

### Benutzer löschen 

```
# Löschen als unprivilegierter Nutzer mit sudo-Rechten 
sudo userdel training 
```
