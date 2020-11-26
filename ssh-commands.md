# SSH Kommandos auf Zielssystem ausführen 

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
