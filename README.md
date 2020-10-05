# Linux Einführung 

   1. [Grundlagen](#1-grundlagen)
   1. [Bash - Programmierung](#2-bash---programmierung) 
   1. [Arbeiten auf der Bash](arbeiten-auf-der-bash.md#)
   1. [Grundlegende Dateioperationen](grundlegende-dateioperationen.md)
   1. [Hilfe](hilfe.md)
   1. [Benutzer](benutzer.md)
   1. [Ausgabe von Dateien](ausgabe-von-dateien.md)
   1. [Ausgabe von gepackten Files / Entpacken von Files](ausgabe-von-gepackten-files.md)
   1. [Suche](suche.md)

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


