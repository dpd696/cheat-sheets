# Cron

A CRON expression is simply a string consisting of six fields that each define a specific unit of time. 

They are written in the following format:

```
{second} {minute} {hour} {day} {month} {day of the week}
```

COMMAND | DESCRIPTION
---|---
crontab -e | # editing the current user’s crontab file
crontab -l | # listing the current user’s crontab file 
crontab -r | # removing the current user’s crontab file 

---
## Values

The following values are allowed within each date/time unit placeholder.

| Field | Allowed Values | Description |
|---|---|---|
| {second} | 0-59 | Trigger every {second} second(s) |
| {minute} | 0-59 | Trigger every {minute} minute(s) | 
| {hour} | 0-23 | Trigger every {hour} hour(s) |
| {day} | 1-31 | Trigger every {day} day(s) of month |
| {month} | 1-12 | Trigger every {month} month(s) |
| {day of week} | 0-6 | MON-SUN Trigger on specific {day of week} |

---
## Special Characters

Additionally you can also use the following special characters to build more advanced expressions:

| Special Character | Description |
|---|---|
| `*` | Trigger on tick of every time unit |
| `,` | List separator |
|`–` | Specifies a range |
| `/` | Defines an increment |

---
## Examples

COMMAND | DESCRIPTION
---|---
$ * * * * * /path_to_task_to_run.sh | # run every minute
$ 15 * * * * /path_to_task_to_run.sh | # run every hour at minute 15
$ 30 18 * * * /path_to_task_to_run.sh | # run every day at 6:30 PM
$ 3 22 * * 1 /path_to_task_to_run.sh | # run every Monday at 10:03 PM
$ 10 6 1 * * /path_to_task_to_run.sh | # run on the 1st of every Month at 6:10 AM
$ 1,20,35 * * * * /path_to_task_to_run.sh | # run every hour at minute 1, 20 and 35
$ 10 */2 * * * /path_to_task_to_run.sh | # run every two hour at minute 10
@yearly     /path_to_task_to_run.sh | # run once a year on the 1st of January at midnight
@monthly    /path_to_task_to_run.sh | # run once a month at midnight on the first day of the month
@daily      /path_to_task_to_run.sh | # run once a week at midnight on Sunday
@hourly     /path_to_task_to_run.sh | # once an hour at the beginning of the hour
@reboot     /path_to_task_to_run.sh | # run at boot time

##All scripts in following directories will run as root at that interval:
```
/etc/cron.hourly
/etc/cron.daily  
/etc/cron.hourly  
/etc/cron.monthly
/etc/cron.weekly
```