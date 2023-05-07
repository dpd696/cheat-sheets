# NETSTAT and SS

## displaying all open ports and connections

```
sudo netstat -tupan
sudo ss -tupan
netstat -tupan | grep :80   # => checking if port 80 is open
```

---
# LSOF

## listing all files that are open

```
lsof
```

---
## listing all files opened by the processes of a specific user

```
lsof -u username
```

---
## listing all files opened by a specific process

```
lsof -c sshd
```

---
## listing all files that have opened TCP ports

```
lsof -iTCP -sTCP:LISTEN
lsof -iTCP -sTCP:LISTEN -nP
```