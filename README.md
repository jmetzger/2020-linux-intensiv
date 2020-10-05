# Linux Einführung 

   1. [Grundlagen](#1-grundlagen)
   1. [Bash - Programmierung](#2-bash-programmierung) 
   1. [MySQL - Galera - Cluster](suche.md#)

## 1 Grundlagen

### Wann Linux, wann Windows ? 

https://www.computerweekly.com/de/meinung/Das-beste-Server-Betriebssystem-Vergleich-zwischen-Linux-und-Windows#:~:text=Linux%20kommt%20im%20Data%20Center,viele%20verschiedene%20Einsatzzwecke%20zu%20verwenden.

## 2 Bash - Programmierung

### Bash Programming - Howto's 

https://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html
https://tldp.org/LDP/abs/html/

### Bash Script - Example 

```
# /home/nobleprog/test.sh 


#!/bin/bash
#
#ls -la
# Long Option with value 
ls -la | head --lines=4
# Short option with value 
ls -la | tail -n 4
```

### Return Values 

```
# Every command has a return value 
# 0 = success 
# 0 <> failure 
example 
date
echo $?
0

keinbefehl
echo $?
127 
```

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


## 4 Grundlegende Dateioperationen

### Verzeichnis wechseln und Liste anzeigen 
```
# Verzeichnis wechseln 
cd /

# In das Heimat oder User-Verzeichnis wechseln
cd

# Ein Verzeichnis höher wechseln 
cd ..
```

### In welchem Verzeichnis bin ich ?

```
# Verzeichnis anzeigen, in dem ich bin 
pwd 
```

### Verzeichnis - Liste 

```
# Verzeichnisliste anzeigen 
ls -l 

# Liste mit versteckten Dateien 
ls -la

# Listing seitenweise anzeigen (Pager) 
ls -la  | less 

```

### Hintergrund zu . und .. im Verzeichnis 

```
## Hintergrund '.' und '..' 

. = aktuelles Verzeichnis 
.. = übergeordnetes Verzeichnis 

ls -la training
total 8
drwxrwxr-x  2 nobleprog nobleprog 4096 Oct  5 09:22 .
drwxr-xr-x 24 nobleprog nobleprog 4096 Oct  5 09:22 ..
```

### Verzeichnis/Datei anlegen, löschen und umbenennen 

```
# mit relativem Pfad / im aktuellen Verzeichnis 
mkdir training  
mkdir /home/user/training2 

# Verzeichnisstruktur anlegen (-p)  
mkdir -p daten/2020/dezember 
```

```
# Leeres Verzeichnis löschen 
rmdir verzeichnisname 
```

### Datei anlegen/löschen  

```
# Anlegen Datei 
touch dateiname

# Löschen mit Nachfrage 
rm -i dateiname 

# Löschen ohne Nachfrage 
rm dateiname 

# Ausgabe - keine Berechtigung 
nobleprog@jochen-g14d:/$ rm vmlinuz.old 
rm: cannot remove 'vmlinuz.old': Permission denied

# Löschen von Verzeichnissen
rm -r verzeichnis 
rm -R verzeichnis 
```

```
# Umbenennen und Kopieren Datei/Verzeichnis
mv dateiname neuer_dateiname 
mv verzeichnis neues_verzeichnis 
cp dateiname neuer_dateiname

# Beim Kopieren alle Rechte übernehmen und Verzeichnis kopieren.
# in den meisten fällen besser als nur:
# cp verzeichnis -> weil rechte übernommen werden. 
cp -a verzeichnis verzeichnis_neu
cp -a datei datei_neu 
```

### Verzeichnis kopieren

```
cp -r verzeichnis verteichnis_neu 
```


## 5 Hilfe

### Man - Seiten 

```
man ls 
# (Verlassen mit q )

### Suchen in der Hilfe 
/suchbegriff + Enter 
# nächster Vorkommen Taste ->  
n (wie next) 

# hilfeseite des man - kommandos 
man man 
```

### --help / -h - Schalter in Befehlen 

```
befehl --help 
oder 
befehl -h 

Beispiel:
ls --help 
```

### Befehle suchen mit apropos 

```
# nach befehlen suchen 
apropos befehl 
# copy soll nur in der Überschrift vorkommen 
# Ausgabe durch pager 
apropos copy files | grep copy | less

```

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

## 7 Ausgabe von Dateien 

### Cat und Less (pager) 
```
cat filename 
# mit pager
cat filename | less  
# direkt mit pager 
less filename 
```
