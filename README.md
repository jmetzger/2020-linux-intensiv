# Linux Einführung 

   1. Grundlagen
      * [Grundlagen](grundlagen.md)
   1. Systemd und Journalctl  
      * [Systemd](systemd.md)
      * [journalctl](journalctl.md)
   1. Bash 
      * [Bash - Grundlegende Befehle der Systemadministration](grundlegende-befehle.md)
   1. Kernel
      * [Kernel Parameter](kernel-params.md)
      * [Kernel kompilieren](kernel-kompilieren.md)
   1. Find
      * [Find](find.md)
   1. Verzeichnisse und Dateien 
      * [Grundlegende Ordnerstruktur](grundlegende-ordnerstruktur-fhs.md)
      * [Ausgabe von Dateien](ausgabe-von-dateien.md)
      * [Ausgabe von gepackten Files / Entpacken von Files](ausgabe-gepackte-files.md)
   1. Suche und Filtern 
      * [Suche](suche.md)
      * [Übung mit Dateien filtern](uebung-dateien.md) 
   1. Paketmanager (Ubuntu/Debian) und Software installieren
      * [apt/dpkg](dpkg-apt.md)
      * [Software installieren](software-installieren.md)
      * [dnf](dnf.md) 
      * [unattendend upgrades](unattended-upgrades.md)
   1. Filesysteme  
      * [xfsdump und -restore](xfsdump-und-restore.md) 
   1. Sudo 
      * [sudo](sudo.md)
   1. ssh und scp 
      * [ssh](ssh.md) 
      * [scp](scp.md)
      * [ssh Kommandos auf Zielsystem ausführen](ssh-commands.md) 
   1. Bash und Bash-Programmierung 
      * [Strings escapen](strings-escapen.md)
      * [Arbeiten auf der Bash](arbeiten-auf-der-bash.md#)
   1. Editoren
      * [Vi/vim](vi.md)
   1. Logs 
      * [debugging log-files ](debugging-logs.md) 
   1. Firewall
      * [firewalld](firewalld.md)
      * [ufw](ufw.md) 
   1. Hilfe 
      * [Hilfe](hilfe.md)
   1. Benutzer verwalten 
      * [Benutzer](benutzer.md)
   1. Hilfreiche Programme 
      * [Hilfreiche Programme](hilfreiche-programme.md) 
   1. Prozesse
       * [Prozesse](prozesse.md)
   1. Dienste verwalten 
      * [Dienste](dienste.md) 
   1. Fragen,Tipps und Tricks
      * [Questions](questions.md)
      * [Tipps und Tricks](tipps-tricks.md) 



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

### If - Schleife 

```
if /bin/true
  then
     echo 'then'
     exit 0
  else 
     echo 'else'
     exit 1
fi
```

### Beispiel-Script 

```
#!/bin/bash 

#echo 'scriptname:'$0
#echo 'param1:'$1
#echo 'alle params:'$@
#echo 'anzahl:'$#
source $HOME/config.sh
# . $HOME/config.sh

if test ! -d $DATEN 
then
  echo "Verzeichnis $DATEN existiert nicht. Es wird angelegt" >> $LOGTO
  mkdir $DATEN
else
  echo "Verzeichnis $DATEN existiert. Alles gut" >> $LOGTO
fi 

let i=0

while test $i -lt 1000000000000000
do
  let i=i+1
  DATUM=$(date)
  echo $DATUM" Zahl:"$i >>  $LOGTO
  echo $DATUM" Schlafe fuer 5 Sekunden" >> $LOGTO 
  sleep 5
done

```
