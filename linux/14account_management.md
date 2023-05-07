# Account Management

## IMPORTANT FILES
```
/etc/passwd       # => users and info: username:x:uid:gid:comment:home_directory:login_shell
/etc/shadow       # => users' passwords
/etc/group        # => groups
```

## Creating A User Account
useradd [OPTIONS] username
OPTIONS | DESCRIPTION
---|---
-m | => create home directory
-d directory | => specify another home directory 
-c "comment" | Add Comment
-s | shell
-G | => specify the secondary groups (must exist)
-g | => specify the primary group (must exist)

Exemple:
```
useradd -m -d /home/john -c "C++ Developer" -s /bin/bash -G sudo,adm,mail john
```

## Changing A User Account
COMMAND | DESCRIPTION
---|---
usermod [OPTIONS] username | => uses the same options as useradd

Example:
```
usermod -aG developers,managers john        # => adding the user to two secondary groups
```

## Deleting A User Account
```
userdel -r username     # => -r removes user's home directory as well
```

## Creating A Group
```
groupadd group_name
```

## Deleting A Group
```
groupdel group_name
```

## Displaying All Groups
```
cat /etc/group
```

## Displaying The Groups A User Belongs To
```
groups
```

## Creating Admin Users
Add The User To Sudo Group In Ubuntu And Wheel Group In Centos
```
usermod -aG sudo john
```


## Monitoring Users
COMMAND | DESCRIPTION
---|---
who -H | => displays logged in users
id | => displays the current user and its groups
whoami | => displays EUID

## Listing Who’S Logged In And What’S Their Current Process.
```
w
uptime
```

## Printing Information About The Logins And Logouts Of The Users
```
last
last -u username
```