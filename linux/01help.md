# Getting Help in Linux

## MAN Pages

man - an interface to the system reference manuals

```
man command     # => Ex: man ls
```

The man page is displayed with the less command

---
## SHORTCUTS:

```
# h         => getting help
# q         => quit
# enter     => show next line
# space     => show next screen
# /string   => search forward for a string
# ?string   => search backwards for a string
# n / N     => next/previous appearance
```

---
## Checking if a command is shell built-in or executable file

```
type rm        # => rm is /usr/bin/rm
type cd        # => cd is a shell builtin
```

---
## Getting help for shell built-in commands

```
help command    # => Ex: help cd
command --help  # => Ex: rm --help
```

---
## Searching for a command, feature or keyword in all man Pages

```
man -k uname
man -k "copy files"
apropos passwd
```

---