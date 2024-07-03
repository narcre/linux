## Zip
```
apt install zip unzip

zip -r compressed_filename.zip foldername
```

```
unzip x.zip
```

## Tar
```
tar -xvf filename.tar.xz
tar -xvzf harbor-offline-installer-v2.4.1.tgz
tar –xvzf documents.tar.gz





compress and uncompress

sudo tar -czvf narcre.tar.gz python3.8/

sudo tar -xzvf narcre.tar.gz 
```
###### compress directory and copy it into remote host
```
tar zcvf - /tmp/temp/ | ssh user@x.x.x.x "cat > /backup/server/mytar.tar.gz"
```

## rar
```
apt install unrar
unrar e filename.rar

```
