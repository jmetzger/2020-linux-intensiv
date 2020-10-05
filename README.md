# Linux Einführung 

## Wann Linux, wann Windows ? 

https://www.computerweekly.com/de/meinung/Das-beste-Server-Betriebssystem-Vergleich-zwischen-Linux-und-Windows#:~:text=Linux%20kommt%20im%20Data%20Center,viele%20verschiedene%20Einsatzzwecke%20zu%20verwenden.


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

## Verzeichnis anlegen, löschen und umbenennen 

```

# mit relativem Pfad / im aktuellen Verzeichnis 
mkdir training  
mkdir /home/user/training2 

## Hintergrund '.' und '..' 
```


```
. = aktuelles Verzeichnis 
.. = übergeordnetes Verzeichnis 

ls -la training
total 8
drwxrwxr-x  2 nobleprog nobleprog 4096 Oct  5 09:22 .
drwxr-xr-x 24 nobleprog nobleprog 4096 Oct  5 09:22 ..
```

## Datei anlegen 

```
touch dateiname 
```

## Hilfe ## 

```
man ls 
# (Verlassen mit q )

### Suchen in der Hilfe 
/suchbegriff + Enter 
# nächster Vorkommen Taste ->  
n (wie next) 

befehl --help 
oder 
befehl -h 

Beispiel:
ls --help 

```

## Benutzer ##

```
# Wer bin ich / Unter welchem Benutzer bin ich eingeloggt  
whoami 

# Mehr über mich
id
```
