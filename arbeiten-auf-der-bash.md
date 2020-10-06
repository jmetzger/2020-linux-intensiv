# Linux - Einführung 

## 3 Arbeiten auf der Bash 

### Bash Specials 

```
# Zeigt Heimatverzeichnis des aktuell eingeloggten Nutzers an 
echo ~
# Ausgeführte Befehle während meiner Session 
history 
# Bestimmten Befehl aus der History ausführen:
# !nr 
# Beispiel 
!244  # Achtung wird direkt ausführt 
```

### Umgebungsvariablen anzeigen 

```
# Alle 
env 
# eine spezielle, z.B 
echo $PATH 
```

### Ein Programm verlassen 

```
Variante 1: 
STRG + c (gleichzeitig drücken) 

oder
Variante 2:
q 

oder 
Variante 3:
Termin schliessen 

=> eines von beiden geht eigentlich immer 
```

### PATH / Wo werden Kommandos gesucht ? 

```
env
echo $PATH 
which ls 
which command 
```

### Variable setzen 

```
LISTE=ls 
echo $LISTE 
# Kommando ausführen 
$LISTE 
# mit Argumenten 
$LISTE -la 
```

### Variablen auswerten (einfache und doppelte Hochkommas)

```
# Einfache Hochkommas -> kein Auswertung 

root@jochen-g14d:/var/log# echo 'Das ist mein Pfad $PATH' 

root@jochen-g14d:/var/log# echo "Das ist mein Pfad $PATH" 
Das ist mein Pfad /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
root@jochen-g14d:/var/log# echo "Das ist mein Pfad $(date)" 
Das ist mein Pfad Mon 05 Oct 2020 01:20:57 PM UTC
root@jochen-g14d:/var/log# echo "Das ist mein Pfad $PATH" 
```

### In den root-Benutzer (Administrator) wechseln 


```
# Hat alle rechte wie Administrator unter Windows 
sudo su 

# oder mit ins Heimatverzeichnis wechseln
sudo su -
```

### Variablen setzen und Variablen mit Funktionsausgaben setzen (Ausgabe des ausgeführten Programms) 

```
date 
# keine Ausgabe des Datums 
DATUM=date
# Ausgabe des datums 
DATUM=$(date) 
# direkt im echo 
echo $(date) 
```

```
# Direkt in ein File schreiben 
root@jochen-g14d:/var/log# echo $(date)' eine wunderbare Zeit' >> training.log 
root@jochen-g14d:/var/log# cat training.log
heute ist ein schöner tag
Mon 05 Oct 2020 01:16:15 PM UTC eine wunderbare Zeit
root@jochen-g14d:/var/log# 
```

### Gehört kommando zur shell oder ist es eigenständig (oder alias) 

```
nobleprog@jochen-g14d:~$ type umask
umask is a shell builtin
nobleprog@jochen-g14d:~$ type ls
ls is aliased to `ls --color=auto'
nobleprog@jochen-g14d:~$ type cd
cd is a shell builtin
nobleprog@jochen-g14d:~$ type grep
grep is aliased to `grep --color=auto'
nobleprog@jochen-g14d:~$ type less
less is /usr/bin/less
nobleprog@jochen-g14d:~$ 
```

### Shell Expansion mit '*' 

```
echo new*
newdir newdir2 newfile newfile2
nobleprog@jochen-g14d:~$ ls -la newdir newdir2 newfile newfile2 
-rw-rw-r-- 1 nobleprog nobleprog    0 Oct  6 11:11 newfile
---------- 1 nobleprog nobleprog    0 Oct  6 11:17 newfile2

newdir:
total 8
drwxrwxr-x  2 nobleprog nobleprog 4096 Oct  6 11:13 .
drwxr-xr-x 27 nobleprog nobleprog 4096 Oct  6 11:17 ..
ls: cannot open directory 'newdir2': Permission denied
```
