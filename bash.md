## DateTime
```
PS1="[\u@\h \D{%Y-%m-%d  %H:%M:%S}]\$ "
PS1='$(whoami)@server-6:${PWD} # '
```

## History
```
set +o history

echo 'set +o history' >> ~/.bashrc
. ~/.bashrc

echo 'set +o history' >> /etc/profile
```
