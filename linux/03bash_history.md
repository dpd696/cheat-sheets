# Bash History

COMMAND | DESCRIPTION
---|---
history | # showing the history
history -d 100 | # removing a line (ex: 100) from the history
history -c | # removing the entire history
echo $HISTFILESIZE | # printing the no. of commands saved in the history file (~/.bash_history)
echo $HISTSIZE | # printing the no. of history commands saved in the memory
!! | # rerunning the last command from the history
!20 | # running  a specific command from the history (ex: the 20th command)
!-10 | # running the last nth (10th) command from the history
!abc | # running the last command starting with abc 
!abc:p | # printing the last command starting with abc 
CTRL + R | # reverse searching into the history
HISTTIMEFORMAT="%d/%m/%y %T " | # recording the date and time of each command in the history