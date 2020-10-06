# Linux Einführung 

   1. [Grundlagen](#1-grundlagen)
   1. [Bash - Programmierung](#2-bash---programmierung) 
   1. [Arbeiten auf der Bash](arbeiten-auf-der-bash.md#)
   1. [Grundlegende Dateioperationen](grundlegende-dateioperationen.md)
   1. [Hilfe](hilfe.md)
   1. [Benutzer](benutzer.md)
   1. [Ausgabe von Dateien](ausgabe-von-dateien.md)
   1. [Ausgabe von gepackten Files / Entpacken von Files](ausgabe-gepackte-files.md)
   1. [Suche](suche.md)
   1. [Übung mit Dateien filtern](uebung-dateien.md)

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

### Testing conditions with test ###

```
nobleprog@jochen-g14d:~$ man test
nobleprog@jochen-g14d:~$ man test
# Test for directory
nobleprog@jochen-g14d:~$ test -d /etc
nobleprog@jochen-g14d:~$ echo $?
0
nobleprog@jochen-g14d:~$ test -d /etc2
nobleprog@jochen-g14d:~$ echo $?
1
# Does Directory not exist -> true = 0 
nobleprog@jochen-g14d:~$ test ! -d /etc2
nobleprog@jochen-g14d:~$ echo $?
0
nobleprog@jochen-g14d:~$ man test
nobleprog@jochen-g14d:~$ [ ! -d /etc2 ]
nobleprog@jochen-g14d:~$ echo $?
0
nobleprog@jochen-g14d:~$ man test

# Be careful with spaces after [ and before ] (must have) 
nobleprog@jochen-g14d:~$ [! -d /etc2]
[!: command not found
nobleprog@jochen-g14d:~$ [ ! -d /etc2 


```


