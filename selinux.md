# selinux basics 

## 

```
# ist selinux aktiviert
sestatus
# selinux während der laufzeit durch root deaktivieren
setenforce 0
# wie ist der aktuelle modus 
getenforce
#Permissive
# auf enforcing 
setenforce 1
getenforce
#Enforcing
