# WGET

- Installing wget
```
apt install wget        # => Ubuntu
dnf install wget        # => CentOS
```

---
## Download A File In The Current Directory
wget https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
```

---
## Resuming The Download 

```
wget -c https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
```

---
## Saving The File Into A Specific Directory

```
mkdir kali
wget -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
```

---
## Limiting The Rate (Bandwidth)

```
wget --limit-rate=100k -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
```

---
## Downloading More Files 

```
wget -i urls.txt      # urls.txt contains urls
```

---
## Starting The Download In The Background

```
wget -b -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
tail -f wget-log        # => checking its status
```

---
## Getting An Offline Copy Of A Website

```
wget --mirror --convert-links --adjust-extension --page-requisites --no-parent http://example.org
wget -mkEpnp http://example.org
```

