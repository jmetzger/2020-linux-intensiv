# ufw (uncomplicated firewall)

## enable ufw / if not enabled yet

```
ufw status
ufw enable 
ufw status
ufw disable
```

## ipv6 or not ? 

```
/etc/default/ufw 
IPV6=no 
```

## check status and the current policies 

```
ufw status verbose
```

## set default policies 

```
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

## Dienst erlauben 

```
# ssh wird über /etc/services gefunden 
sudo ufw allow ssh
# alternativ 
sudo ufw allow 22
```

## Portbereiche 

```
sudo ufw allow 6000:6007/tcp
sudo ufw allow 6000:6007/udp
```

## Port - Ranges 

```
sudo ufw allow 6000:6007/tcp
sudo ufw allow 6000:6007/udp
```

## Subnetze
```
sudo ufw allow from 203.0.113.0/24
# or specific port 
sudo ufw allow from 203.0.113.0/24 to any port 22
```

## zu spezifischer Netzwerkschnittstelle 
```
sudo ufw allow in on eth0 to any port 80
```

## Deny - Verbindung
```
sudo ufw deny http
sudo ufw deny from 203.0.113.4
```

## Löschen von Regeln 
```
# nach nummer
sudo ufw status numbered
sudo ufw delete 2

# nach tatsächlicher regel 
sudo ufw delete allow http

```

## Prüfen von Regeln 

```
sudo ufw status verbose
```

## Zurücksetzen der Regeln 

```
ufw reset 
```

## ufw - port weiterleitung 

  * https://qastack.com.de/server/238563/can-i-use-ufw-to-setup-a-port-forward

## References:

  * https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-20-04-de
