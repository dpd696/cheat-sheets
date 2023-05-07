# Finding Files (find, locate)

## LOCATE
Updating the locate db
```
sudo updatedb
```

## Displaying Statistics
```
locate -S
``` 

## Finding File by Name
```
locate filename         # => filename is expanded to *filename*
locate -i filename      # => the filename is case insensitive
locate -b '\filename'   # => finding by exact name
```

## Finding Using the Basename 
```
locate -b filename
```

## Finding Using Regular Expressions
```
locate -r 'regex'
```

## Checking that the file exists
```
locate -e filename 
```

## Showing command path
```
which command
which -a command
```


## FIND
find PATH OPTIONS
```
# Example: find ~ -type f -size +1M     # => finding all files in ~ bigger than 1 MB 
```
Options:
```
-type f, d, l, s, p
-name filename
-iname filename   # => case-insensitive
-size n, +n, -n
-perm permissions
-links n, +n, -n
-atime n, -mtime n, ctime n
-user owner
-group group_owner
```