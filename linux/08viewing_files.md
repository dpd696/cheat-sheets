# Viewing files (cat, less, more, head, tail, watch)

## Displaying the contents of a file
cat filename
COMMAND | DESCRIPTION
---|---
cat filename1 filename2 | # displaying more files
cat -n filename | # displaying the line numbers
cat filename1 filename2 > filename3 | # concatenating 2 files

## Viewing a file using less
less filename
LESS SHORTCUTS | DESCRIPTION
---|---
h | => getting help
q | => quit
enter | => show next line
space | => show next screen
/string | => search forward for a string
?string | => search backwards for a string
n / N | => next/previous appearance

## Using tail
less filename
COMMAND | DESCRIPTION
---|---
tail filename | # showing the last 10 lines of a file
tail -n 15 filename | # showing the last 15 lines of a file
tail -n +5 filename | # showing the last lines of a file starting with line no. 15
tail -f filename | # showing the last 10 lines of the file in real-time

## Using head
less filename
COMMAND | DESCRIPTION
---|---
head filename | # showing the first 10 lines of a file
head -n 15 filename | # showing the first 15 lines of a file

## Using watch
less filename
COMMAND | DESCRIPTION
---|---
watch -n 3 ls -l | # running repeatedly a command with refresh of 3 seconds