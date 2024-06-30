## rsync options
```
-vr --verbose --recursive
-r  => or -a
--exclude=file or directory(use , for multi dir)
--dry-run or -n  ==> use -avn
--delete ==> for sync if files deleted from source
-azP ==> zip file for transfer (optimizing the bandwidth) with progress bar
```

## Backup & Restore Snario

##### Backup
```
DESTINATIONS="192.168.10.13"

for HOST in ${DESTINATIONS}; do
	rsync -a sample-dir/ -e "ssh -i $HOME/.ssh/somekey" databackup@${HOST}:/home/databackup/sample-dir --log-file=result
done
```
##### Restore
```
DESTINATION="192.168.10.3"
LOCAL_PATHS="/home/databackup/sample-dir /home/databackup/mydir"
DESTINATION_PATH="/home/databackup/"

for PA in ${LOCAL_PATHS}; do
	rsync -a ${PA}  databackup@${DESTINATION}:${DESTINATION_PATH}
done
```
