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
