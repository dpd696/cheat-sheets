# Service Management using systemd and systemctl

---
## Showing Info About The Boot Process

```
systemd-analyze
systemd-analyze blame
```

---
## Listing All Active Units Systemd Knows About

```
systemctl list-units
systemctl list-units | grep ssh
```

---
## Checking The Status Of A Service

```
sudo systemctl status nginx.service
```

---
## Stopping A Service

```
sudo systemctl stop nginx
```

---
## Starting A Service

```
sudo systemctl start nginx
```

---
## Restarting A Service

```
sudo systemctl restart nginx
```

---
## Reloading The Configuration Of A Service

```
sudo systemctl reload nginx
sudo systemctl reload-or-restart nginx
```

---
## Enabling To Start At Boot Time

```
sudo systemctl enable nginx
```

---
## Disabling At Boot Time

```
sudo systemctl disable nginx
```

---
## Checking If It Starts Automatically At Boot Time

```
sudo systemctl is-enabled nginx
```

---
## Masking A Service (stopping and disabling it)

```
sudo systemctl mask nginx
```

---
## Unmasking A Service

```
sudo systemctl unmask nginx
```