## Backup & Restore Snario

##### Backup
```
DESTINATIONS="192.168.10.13"

for HOST in ${DESTINATIONS}; do
	rsync -a sample-dir/  databackup@${HOST}:/home/databackup/sample-dir --log-file=result
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
