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
