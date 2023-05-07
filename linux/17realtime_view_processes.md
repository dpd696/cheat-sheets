# Dynamic Real-Time View of Processes(top)

## Starting Top

```
top
```

TOP SHORTCUTS | DESCRIPTION
---|---
h | => getting help
space | => manual refresh
d | => setting the refresh delay in seconds
q | => quitting top
u | => display processes of a user
m | => changing the display for the memory
1 | => individual statistics for each CPU
x/y | => highlighting the running process and the sorting column
b | => toggle between bold and text highlighting
< | => move the sorting column to the left
> | => move the sorting column to the right
F | => entering the Field Management screen 
W | => saving top settings

## Running Top In Batch Mode (3 Refreshes, 1 Second Delay)

```
top -d 1 -n 3 -b > top_processes.txt
```

## Interactive Process Viewer (Top Alternative)

Installing htop
```
sudo apt update && sudo apt install htop    
htop
```