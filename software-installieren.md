## 15 Software Installieren 

### Debian / Ubuntu 

```
# apt ist der Paketmanager 
apt search apache2 
# seitenweise ausgabe
apt search apache2 | less 
# installieren 
apt update 
apt install apache2 
```

```
# Repoositories, d.h. wo liegt die Software
# wird unter /etc/apt/source.list gepflegt
```

```
apt install 
... installiert die Pakete (.deb - Dateien) und löst Abhängigkeiten automatisch auf
```

### Debian/Ubuntu install with dpkg 

```
# Download Package 
wget https://repo.percona.com/apt/percona-release_latest.$(lsb_release -sc)_all.deb

ls -la percona-release_latest.focal_all.deb 
-rw-rw-r-- 1 nobleprog nobleprog 11618 Sep  2 14:24 percona-release_latest.focal_all.deb

dpkg -i percona-release_latest.focal_all.deb
```

```
# rechner1 -> rechner2
# ins /tmp schreiben geht immer 
training@rechner1$ scp paket.deb user@rechner2:/tmp 

# auf rechner2 
training@rechner2$ cd /tmp; sudo dpkg -i paket.deb 
```

### Debian/Update updaten / neuester Stand 

```
apt update
apt dist-update 
```
