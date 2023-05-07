# The ls Command

ls [OPTIONS] [FILES]

## listing the current directory
COMMAND | DESCRIPTION
---|---
~ | => user's home directory
. | => current directory
.. | => parent directory
ls | 
ls . | 
ls ~ /var / | # listing more directories
ls -l ~ | # -l => long listing
ls -la ~ | # -a => listing all files and directories including hidden ones
ls -1 /etc | # -1 => listing on a single column
ls -ld /etc | # -d => displaying information about the directory, not about its contents
ls -h /etc | # -h => displaying the size in human readable format
ls -Sh /var/log | # -S => displaying sorting by size
du -sh ~ | # Note: ls does not display the size of a directory and all its contents. Use du instead
ls -lX /etc | # -X => displaying sorting by extension
ls --hide=*.log /var/log | # --hide => hiding some files
ls -lR ~ | # -R => displaying a directory recursively
ls -li /etc | # -i => displaying the inode number