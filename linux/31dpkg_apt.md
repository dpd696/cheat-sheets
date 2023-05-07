# Software Management (dpkg and apt)

---
# DPKG

---
## Getting Info About A Deb File

```
dpkg --info google-chrome-stable_current_amd64.deb
```

---
## Installing An Application From A Deb File

```
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

---
## List All Installed Programs

```
dpkg --get-selections
dpkg-query -l
```

---
## Filtering The Output

```
dpkg-query -l | grep ssh
```

---
## Listing All Files Of An Installed Package

```
dpkg-query -l | grep ssh
dpkg -L openssh-server
```

---
## Finding To Which Package A File Belongs 

```
which ls
dpkg -S /bin/ls
    coreutils: /bin/cp
```

---
## Removing A Package

```
sudo dpkg -r google-chrome-stable
```

---
## Purging A Package

```
sudo dpkg -P google-chrome-stable
```

---
# APT

---
## Updating The Package Index (doesn't install/uninstall/update any package)

```
sudo apt update
```

---
## Installing Or Updating A Package Named apache2

```
sudo apt install apache2
```

---
## Listing All Upgradable Packages

```
sudo apt list --upgradable
```

---
## Upgrading All Applications

```
sudo apt full-upgrade
sudo apt full-upgrade -y        # => assume yes to any prompt (useful in scripts)
```

---
## Removing A Package

```
sudo apt remove apache2
```

---
## Removing A Package And Its Configurations

```
sudo apt purge apache2
```

---
## Removing Dependencies That Are Not Needed Anymore

```
sudo apt autoremove
```

---
## Removing The Saved Deb Files From The Cache Directory (var/cache/apt/archives)

```
sudo apt clean
```

---
## Listing All Available Packages

```
sudo apt list
sudo apt list | wc -l
```

---
## Searching For A Package

```
sudo apt list | grep nginx
```

---
## Showing Information About A Package

```
sudo apt show nginx
```

---
## Listing All Installed Packages

```
sudo apt list --installed
```