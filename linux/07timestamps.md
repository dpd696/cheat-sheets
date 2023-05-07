# File Timestamps and Date

COMMAND | DESCRIPTION
---|---
ls -lu | # displaying atime
ls -l | # displaying mtime
ls -lt | # displaying mtime
ls -lc | # displaying ctime
stat file.txt | # displaying all timestamps
ls -l --full-time /etc/ | # displaying the full timestamp
touch file.txt | # creating an empty file if it does not exist, update the timestamps if the file exists
touch -a file | # changing only the access time to current time
touch -m file | # changing only the modification time to current time
touch -m -t 201812301530.45 a.txt | # changing the modification time to a specific date and time
touch -d "2010-10-31 15:45:30" a.txt | # changing both atime and mtime to a specific date and time
touch a.txt -r b.txt | # changing the timestamp of a.txt to those of b.txt
date | # displaying the date and time
cal | # showing this month's calendar
cal 2021 | # showing the calendar of a specific year
cal 7 2021 | # showing the calendar of a specific month and year
cal -3 | # showing the calendar of previous, current and next month
date --set="2 OCT 2020 18:00:00" | # setting the date and time 
ls -l | # displaying the modification time and sorting the output by name.
ls -lt | # displaying the output sorted by modification time, newest files first
ls -ltu | # displaying and sorting by atime
ls -ltu --reverse | # reversing the sorting order