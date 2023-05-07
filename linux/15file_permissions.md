# File Permissions

LEGEND | DESCRIPTION
---|---
LEGEND
u | User
g | Group
o | Others/World
a | all
 | 
r | Read
w | write
x | execute
- | no access

## Displaying The Permissions (ls and stat)

```
ls -l /etc/passwd
-rw-r--r-- 1 root root 2871 aug 22 14:43 /etc/passwd
```

```
stat /etc/shadow
    File: /etc/shadow
    Size: 1721      	Blocks: 8          IO Block: 4096   regular file
    Device: 805h/2053d	Inode: 524451      Links: 1
    Access: (0640/-rw-r-----)  Uid: (    0/    root)   Gid: (   42/  shadow)
    Access: 2020-08-24 11:31:49.506277118 +0300
    Modify: 2020-08-22 14:43:36.326651384 +0300
    Change: 2020-08-22 14:43:36.342652202 +0300
    Birth: -
```

## Changing The Permissions Using The Relative (Symbolic) Mode

```
chmod u+r filename
chmod u+r,g-wx,o-rwx filename
chmod ug+rwx,o-wx filename
chmod ugo+x filename
chmod a+r,a-wx filename
```

## Changing The Permissions Using The Absolute (Octal) Mode


PERMISSIONS | EXAMPLE
u   g   o | User Group Others/World
rwx rwx rwx | chmod 777 filename
rwx rwx r-x | chmod 775 filename
rwx r-x r-x | chmod 755 filename
rwx r-x --- | chmod 750 filename
rw- rw- r-- | chmod 664 filename
rw- r-- r-- | chmod 644 filename
rw- r-- --- | chmod 640 filename

# Setting The Permissions As Of A Reference File

```
chmod --reference=file1 file2
```

# Changing Permissions Recursively

```
chmod -R u+rw,o-rwx filename
```

# SUID (Set User ID)

## Displaying The Suid Permission

```
ls -l /usr/bin/umount 
    -rwsr-xr-x 1 root root 39144 apr  2 18:29 /usr/bin/umount
```

```
stat /usr/bin/umount 
    File: /usr/bin/umount
    Size: 39144     	Blocks: 80         IO Block: 4096   regular file
    Device: 805h/2053d	Inode: 918756      Links: 1
    Access: (4755/-rwsr-xr-x)  Uid: (    0/    root)   Gid: (    0/    root)
    Access: 2020-08-22 14:35:46.763999798 +0300
    Modify: 2020-04-02 18:29:40.000000000 +0300
    Change: 2020-06-30 18:27:32.851134521 +0300
    Birth: -
```

## setting SUID
```
chmod u+s executable_file
chmod 4XXX executable_file      # => Ex: chmod 4755 script.sh
```


# SGID (Set Group ID)

# Displaying The Sgid Permission

```
ls -ld projects/
    drwxr-s--- 2 student student 4096 aug 25 11:02 projects/
```

```
stat projects/
    File: projects/
    Size: 4096      	Blocks: 8          IO Block: 4096   directory
    Device: 805h/2053d	Inode: 266193      Links: 2
    Access: (2750/drwxr-s---)  Uid: ( 1001/ student)   Gid: ( 1002/ student)
    Access: 2020-08-25 11:02:15.013355559 +0300
    Modify: 2020-08-25 11:02:15.013355559 +0300
    Change: 2020-08-25 11:02:19.157290764 +0300
    Birth: -
```

## setting SGID

```
chmod 2750 projects/
chmod g+s projects/
```


# The Sticky Bit 

## Displaying The Sticky Bit Permission

```
ls -ld /tmp/
    drwxrwxrwt 20 root root 4096 aug 25 10:49 /tmp/
```

```
stat /tmp/
    File: /tmp/
    Size: 4096      	Blocks: 8          IO Block: 4096   directory
    Device: 805h/2053d	Inode: 786434      Links: 20
    Access: (1777/drwxrwxrwt)  Uid: (    0/    root)   Gid: (    0/    root)
    Access: 2020-08-22 14:46:03.259455125 +0300
    Modify: 2020-08-25 10:49:53.756211470 +0300
    Change: 2020-08-25 10:49:53.756211470 +0300
    Birth: -
```

# Setting The Sticky Bit

```
mkdir temp
chmod 1777 temp/
chmod o+t temp/
ls -ld temp/
    drwxrwxrwt 2 student student 4096 aug 25 11:04 temp/
```

# UMASK

## Displaying The UMASK

umask 

COMMAND | DESCRIPTION
---|---
umask new_value # => Ex: umask 0022 | # setting a new umask value

## Changing File Ownership (root only)

COMMAND | DESCRIPTION
---|---
chown new_owner file/directory # => Ex: sudo chown john a.txt | # changing the owner
chgrp new_group file/directory | # changing the group owner
chown new_owner:new_group file/directory | # changing both the owner and the group owner
chown -R new-owner file/directory | # changing recursively the owner or the group owner
lsattr filename | # displaying the file attributes
chattr +-attribute filename | #changing the file attributes

## Example

```
sudo chattr +i report.txt
```