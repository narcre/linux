## Replace a To Z in narcre:
```
vim narcre

a
b
abab
c
ca


$ sed -i 's|a|Z|g' narcre


result:

Z
b
ZbZb
c
cZ

```
