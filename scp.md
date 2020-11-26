# Copy files (secure copy) from/to remote systems 

```
scp remotels.sh trn01@10.10.11.126:~/
scp remotels.sh trn01@10.10.11.126:/home/trn01
scp trn01@10.10.11.126:/home/trn01/remotels.sh remotels.sh.bkup

TEMPDIR=$(mktemp -d)
scp -r trn01@10.10.11.126:/home/trn01/ $TEMPDIR
```

