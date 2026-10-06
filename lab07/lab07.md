## Crontab

```bash
darina@MacBook-Pro ~ % mkdir ~/lab7
darina@MacBook-Pro ~ % cd ~/lab7
darina@MacBook-Pro lab7 % nano write_time.sh
darina@MacBook-Pro lab7 % chmod +x write_time.sh
darina@MacBook-Pro lab7 % nano send_notification.py
darina@MacBook-Pro lab7 % chmod +x send_notification.py
darina@MacBook-Pro lab7 % ./write_time.sh
darina@MacBook-Pro lab7 % python3 send_notification.py
Task executed
darina@MacBook-Pro lab7 % cat task_log.txt
Bash script ran at Tue Oct  6 12:21:43 +06 2026
darina@MacBook-Pro lab7 % cat python_task_log.txt
Python script ran at 2026-10-06 12:21:49
darina@MacBook-Pro lab7 % crontab -e
crontab: no crontab for darina - using an empty one
crontab: installing new crontab
darina@MacBook-Pro lab7 % crontab -l
* * * * * /Users/darina/lab7/write_time.sh
* * * * * /usr/bin/python3 /Users/darina/lab7/send_notification.py
darina@MacBook-Pro lab7 % sleep 60
darina@MacBook-Pro lab7 % cat task_log.txt
Bash script ran at Tue Oct  6 12:21:43 +06 2026
Bash script ran at Tue Oct  6 12:26:00 +06 2026
Bash script ran at Tue Oct  6 12:27:00 +06 2026
darina@MacBook-Pro lab7 % cat python_task_log.txt
Python script ran at 2026-10-06 12:21:49
Python script ran at 2026-10-06 12:26:00
Python script ran at 2026-10-06 12:27:00
darina@MacBook-Pro lab7 % 
```