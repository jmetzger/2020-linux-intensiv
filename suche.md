# Linux Einführung 

## Suche 

### Suche in Files mit grep 

```
root@jochen-g14d:/etc# cat services | grep http
# Updated from https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml .
http		80/tcp		www		# WorldWideWeb HTTP
https		443/tcp				# http protocol over TLS/SSL
http-alt	8080/tcp	webcache	# WWW caching service
root@jochen-g14d:/etc# cat services | grep voice box system
grep: box: No such file or directory
grep: system: No such file or directory
root@jochen-g14d:/etc# cat services | grep 'voice box system'
```

```
grep 'voice box system' /etc/services
```

### Suche über alle Files mit grep -r (Schweizer Taschenmesser) 

```
# durchsucht alle order recursive 
grep -r muster /verzeichnis 
```

### Suche - egal ob gross oder klein 

```
grep -ir VOICE /etc | grep services
```

### Suche - alle Zeilen die nicht mit einem # anfangen 

```
cat services | grep -v '^#' 
```

## Entpacken von Files / Ausgaben von gepackten files 

### zcat und gzip -d

```
zcat /var/log/syslog.2.gz 
cp /var/log/syslog.2.gz /root
cd /root
gzip -d syslog.2.gz 
```
