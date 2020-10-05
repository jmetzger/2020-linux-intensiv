# Linux Einführung 

## Wann Linux, wann Windows ? 

https://www.computerweekly.com/de/meinung/Das-beste-Server-Betriebssystem-Vergleich-zwischen-Linux-und-Windows#:~:text=Linux%20kommt%20im%20Data%20Center,viele%20verschiedene%20Einsatzzwecke%20zu%20verwenden.

## Bash Specials 

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

### In den root-Benutzer (Administrator) wechseln 


```
# Hat alle rechte wie Administrator unter Windows 
sudo su 

# oder mit ins Heimatverzeichnis wechseln
sudo su -
```

## Verzeichnis wechseln und Liste anzeigen 
```
# Verzeichnis wechseln 
cd /

# In das Heimat oder User-Verzeichnis wechseln
cd

# Ein Verzeichnis höher wechseln 
cd ..

# Verzeichnis anzeigen, in dem ich bin 
pwd 

# Verzeichnisliste anzeigen 
ls -l 

# Liste mit versteckten Dateien 
ls -la

# Listing seitenweise anzeigen (Pager) 
ls -la  | less 

```

## Verzeichnis/Datei  anlegen, löschen und umbenennen 

```

# mit relativem Pfad / im aktuellen Verzeichnis 
mkdir training  
mkdir /home/user/training2 

# Verzeichnisstruktur anlegen (-p)  
mkdir -p daten/2020/dezember 

```
## Hintergrund '.' und '..' 

```
. = aktuelles Verzeichnis 
.. = übergeordnetes Verzeichnis 

ls -la training
total 8
drwxrwxr-x  2 nobleprog nobleprog 4096 Oct  5 09:22 .
drwxr-xr-x 24 nobleprog nobleprog 4096 Oct  5 09:22 ..
```


```
# Leeres Verzeichnis löschen 
rmdir verzeichnisname 


## Datei anlegen/löschen  

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
```
# in den meisten fällen besser als nur:
# cp verzeichnis -> weil rechte übernommen werden. 
cp -a verzeichnis verzeichnis_neu
cp -a datei datei_neu 
```


# Verzeichnis kopieren
cp -r verzeichnis verteichnis_neu 

```


## Hilfe ## 

```
man ls 
# (Verlassen mit q )

### Suchen in der Hilfe 
/suchbegriff + Enter 
# nächster Vorkommen Taste ->  
n (wie next) 

# hilfeseite des man - kommandos 
man man 


befehl --help 
oder 
befehl -h 

Beispiel:
ls --help 

# nach befehlen suchen 
apropos befehl 
# copy soll nur in der Überschrift vorkommen 
# Ausgabe durch pager 
apropos copy files | grep copy | less

```

## Benutzer ##

```
# Wer bin ich / Unter welchem Benutzer bin ich eingeloggt  
whoami 

# Mehr über mich
id
```

## Ausgabe von Dateien 

```
cat filename 
# mit pager
cat filename | less  
# direkt mit pager 
less filename 
```

## Suche 

### Suche in Files 

```
root@jochen-g14d:/etc# cat services | grep http
# Updated from https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml .
http		80/tcp		www		# WorldWideWeb HTTP
https		443/tcp				# http protocol over TLS/SSL
http-alt	8080/tcp	webcache	# WWW caching service
root@jochen-g14d:/etc# cat services | grep voice box system
grep: box: No such file or directory
grep: system: No such file or directory
root@jochen-g14d:/etc# cat services | grep 'voice box system'
```
