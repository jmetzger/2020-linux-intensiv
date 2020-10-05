# Linux Einführung 

   1. [Grundlagen](#1-grundlagen)
   1. [Bash - Programmierung](#2-bash---programmierung) 
   1. [Arbeiten auf der Bash](arbeiten-auf-der-bash.md#)

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
