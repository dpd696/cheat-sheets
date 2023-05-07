# VIM
 
Modes of operation: Command, Insert, and Last Line Modes.  VIM Config File: ~/.vimrc
 
## Entering the Insert Mode from the Command Mode
COMMAND | DESCRIPTION
---|---
i | => insert before the cursor
I | => insert at the beginning of the line
a | => insert after the cursor
A | => insert at the end of the line
o | => insert on the next line
 
## Entering the Last Line Mode from the Command Mode
:
 
## Returning to Command Mode from Insert or Last Line Mode 
ESC
 
## Shortcuts in Last Line Mode
COMMAND | DESCRIPTION
---|---
w! | => write/save the file
q! | => quit the file without saving
wq! | => save/write and quit
e! | => undo to the last saved version of the file
set nu | => set line numbers
set nonu | => unset line numbers
syntax on|off | 
%s/search_string/replace_string/g | 
 
# Shortcuts in Command Mode
COMMAND | DESCRIPTION
---|---
x | => remove char under the cursor
dd | => cut the current line
5dd | => cut 5 lines
ZZ | => save and quit
u | => undo
G | => move to the end of file
$ | => move to the end of line
0 or ^  => move to the beginning of file
:n (Ex :10) | => move to line n
Shift+v | => select the current line
y | => yank/copy to clipboard
p | => paste after the cursor
P | => paste before the cursor
/string | => search for string forward
?string | => search for string backward
n | => next occurrence
N | => previous occurrence
 
# Opening more files in stacked windows
```
vim -o file1 file2
```
 
# Opening more files and highlighting the differences
```
vim -d file1 file2
```
COMMAND | DESCRIPTION
---|---
Ctrl+w | => move between files