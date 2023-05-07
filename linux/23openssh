# OpenSSH

## Installing OpenSSH (client and server)

- Ubuntu
```
sudo apt update && sudo apt install openssh-server openssh-client
```

- CentOS
```
sudo dnf install openssh-server openssh-clients
```

---
## Connecting To The Server

```
ssh -p 22 username@server_ip        # => Ex: ssh -p 2267 john@192.168.0.100
ssh -p 22 -l username server_ip
ssh -v -p 22 username@server_ip     # => verbose
```

---
## Controlling the SSHd daemon

```
## checking its status
sudo systemctl status ssh       # => Ubuntu
sudo systemctl status sshd      # => CentOS
```

---
## Stopping The Daemon

```
sudo systemctl stop ssh       # => Ubuntu
sudo systemctl stop sshd      # => CentOS
```

---
## Restarting The Daemon

```
sudo systemctl restart ssh       # => Ubuntu
sudo systemctl restart sshd      # => CentOS
```

---
## Enabling At Boot Time

``` 
sudo systemctl enable ssh       # => Ubuntu
sudo systemctl enable sshd      # => CentOS
sudo systemctl is-enabled ssh       # => Ubuntu
sudo systemctl is-enabled sshd      # => CentOS
```

---
# Securing the SSHd daemon

## Change The Configuration File (/etc/ssh/sshd_config) And Then Restart The Server

```
man sshd_config
```

---
Configurations
- Port 2278 # => Change the port
- PermitRootLogin no # => Disable direct root login
- AllowUsers stud u1 u2 john # => Limit Users’ SSH access

### Filter SSH access at the firewall level (iptables)

### Activate Public Key Authentication and Disable Password Authentication

### Use only SSH Protocol version 2

## Other configurations:
- ClientAliveInterval 300
- ClientAliveCountMax 0
- MaxAuthTries 2
- MaxStartUps 3
- LoginGraceTime 20