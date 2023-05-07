# Linux Paths

COMMAND | DESCRIPTION
---|---
. | # => the current working directory
.. | # => the parent directory
~ | # => the user's home directory
cd | # => changing the current directory to user's home directory
cd ~ | # => changing the current directory to user's home directory
cd - | # => changing the current directory to the last directory
cd /path_to_dir | # => changing the current directory to path_to_dir 
pwd | # => printing the current working directory

# Installing Tree

```
sudo apt install tree
```
COMMAND | DESCRIPTION
---|---
tree directory/ | # => Ex: tree .
tree -d . | # => prints only directories
tree -f . | # => prints absolute paths