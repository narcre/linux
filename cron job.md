```
*   *   *   *   *  sh /path/to/script/script.sh
|   |   |   |   |              |
|   |   |   |   |      Command or Script to Execute        
|   |   |   |   |
|   |   |   |   |
|   |   |   |   |
|   |   |   | Day of the Week(0-6)
|   |   |   |
|   |   | Month of the Year(1-12)
|   |   |
|   | Day of the Month(1-31)  
|   |
| Hour(0-23)  
|
Min(0-59)
```

## Add Script Job
```
crontab -e
* * * * * sh /home/backup.sh
```

## Example
```
0 0 * * 0
1 day in every week

0 0 * * *
every day
```
https://crontab-generator.org/ <br>
https://crontab.cronhub.io/
