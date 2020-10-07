## 16 Dienste 

### Dienste verwalten 
```
# Läuft apache? 
systemctl status apache2 
# Apache stoppen 
systemctl stop apache2 
# 
systemctl status apache2 
#
systemctl start apache2 
# Beim Starten des Servers dienst nicht starten
systemctl disable apache2 
# Status --> disabled
systemctl status apache2 
# Enable (Beim Booten des Servers starten) 
systemctl enable apache2

# Welches Services gibt es auf dem System
systemctl list-units -t service 
```

