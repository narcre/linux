 ## TimeZone
 ```
 sudo timedatectl set-timezone Asia/Tehran
 ```
##### formated
```
time=$(date "+%H:%M:%S   %d/%m/%y")
echo $time
```
##### for remove file by date format name in script file
```
time=$(date "+%Y%m%d")
Prev_DATE=$(date +%Y%m%d -d "$time - 1 day")
rm -rf $Prev_DATE 
```
