## Berechtigungen 

### File-Typ 

```
# 
- = File 
d = Verzeichnis 
l = symbolischer Link 
# ab hier -> nice to have 
# Datenbank-Server: Server und Client 
s = Socket (Datenbankverbindung von Client -> Server auf gleichem Server, z.B. MySQL) 
c = Character Device (Maus, Tastatur usw)
b = Block Device (Festplatte, SSD-Platte, CDROM, DVD 
```

### Berechtigungen Buchstaben 

```
r = Read 
w = Write 
x = Execute 
```
### 3 Berechtigungs-Triple 

```
# Für ein File 
      u       g       o
- | - - - | - - - | - - - |

Vollbesetzt:


- | r w x | r w x | r w x | 

```

### chmod - Symbole 

```

Teil 1 Für wen ?
=======
u = user 
g = gruppe
o = others / die anderen / die welt 

alle drei:
a = alle, d.h. user, gruppe, anderen 

Teil 2: Was wollen wir machen 
=======

= genau diese Rechte setzen
- Recht entziehen
+ Recht hinzufügen 

Teil 3: Welches Recht ? 
======

Beispiel:
- Für die anderen -> Recht hinzufügen (+) -> und zwar: Schreiben (w) 

Teil 4: Welche Datei / Welches Verzeichnis 

chmod o+w datei 

```

### chmod - Oktalzahlen 

```

# Zahlen von 0-7 

- | - - - | - - - | - - - | = 0 0 0

# Alle Rechte für Datei 

    4 2 1   4 2 1   4 2 1 
- | r w x | r w x | r w x |  = 7 7 7

# 660

- | r w - | r w - | - - - 

# 755 - Verzeichnis 
      7       5       5
d | r w x | r - x | r - x |

```












