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

###### To view the contents of the myfolder.tar.gz directory
```
tar -tf myfolder.tar.gz
```
###### compress directory and copy it into remote host
```
tar zcvf - /tmp/temp/ | ssh user@x.x.x.x "cat > /backup/server/mytar.tar.gz"
```
###### compress directory and decompress into target
```
sudo tar -zc /tmp/temp/ | ssh ftp@93.118.97.231 tar -zxC /backup-1/server-11/
```

## rar
```
apt install unrar
unrar e filename.rar

```
