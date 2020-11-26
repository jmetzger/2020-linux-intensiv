# SSH Kommandos auf Zielssystem ausführen 

## Einfacher Fall
```
# Fall 1 
COOL=/etc; echo $COOL; ssh trn01@10.10.11.126 'ls -la $COOL'
# auf Zielsystem wird ausgeführt 
ls -la $COOL # Allerdings ist diese Variable dort nicht gesetzt

# Fall 2 
COOL=/etc; echo $COOL; ssh trn01@10.10.11.126 "ls -la $COOL"
# aus Zielsystem wird ausgeführt 
ls -la /etc 

```
## Komplexe Befehle in Variablen ausführen funktioniert nicht ! 

  * https://unix.stackexchange.com/questions/444946/how-can-we-run-a-command-stored-in-a-variable

## Kommandos lokal eingeben und auf zielrechner ausführen (interaktiv) 
```
ssh trn01@10.10.11.126 'bash -s'
```

## Lokales script auf Zielrechner ausführen 
```
ssh trn01@10.10.11.126 'bash -s' < lokalesscript.sh
cat lokalesscript.sh | ssh trn01@10.10.11.126
```
