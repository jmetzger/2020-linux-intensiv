## 12 Prozesse 

### pstree / Baum der Prozess anzeigen 

```
pstree -p | less 

# beispiel mit finden der bash in welchen Prozessen
pstree -p | grep bash 
```

### top / Prozesse interaktiv betracht 

```
top 
q # mit q verlassen 
```

```
Bedeutung:
load average: 0.08, 0.04, 0.00

Wieviel Prozesse warten auf Ausführung durch die CPU in der/den letzten 1 min / 5 min / 15 min 
```

```
# 
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   7107.8 avail Mem

Swap - Daten die auf Festplatte ausgelagert werden, weil zu wenig Arbeitsspeicher da 
=> Achtung: Sollte auf Servern möglichst nicht > 0 sein 
=> Chef, ich brauche mehr Arbeitsspeicher (wenn > 0) 

```

### ps - prozesse anzeigen als Liste 

```
Fall 1: Alle Prozesse anzeigen 

# macht in der Regel als root 
sudo ps aux | less
sudo ps aux 

# Information über bestimmtes kommando (Alle Prozesse)  
ps aux | grep bash

# Wieviel Prozesse 
ps aux | grep bash | wc -l
ps aux | grep -c bash
```

### Beispiel: Prozess-Id (pid) finden 

```
# starter.sh ist das script was wir suchen 
ps aux | grep starter.sh # Info in Spalte 2 (Spalte 1 = user) 
```

### Beenden Programme im Vordergrund 

```
sleep 1000
STRG + c # beendet das programm 
```

