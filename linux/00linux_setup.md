# Linux Setup

Setting up Linux the right way

---
## Installing terminator

```
sudo apt update && sudo apt install terminator
```

---
## Installing OPENSSH

- [OPENSSH](https://github.com/dpd696/cheat-sheets/blob/98ea8c1400db7b4439bdde55972e66f9659c6be7/linux/23openssh.md) - Guide for Installing SSH and Best Practices for Securing SSH

---
## Installing Tree

```
sudo apt update && sudo apt install tree
```

---
## Installing htop

```
sudo apt update && sudo apt install htop 
```

---
## Installing net-tools

```
sudo apt update && sudo apt install net-tools 
```

---
## Alias Setup

- [Alias](https://github.com/dpd696/cheat-sheets/blob/98ea8c1400db7b4439bdde55972e66f9659c6be7/linux/26alias23openssh.md) - Guide for Setting up Aliases for quick Shortcuts to Common Commands.

---
## Setting up CRON TAB for Automatic Updates

```
cron -e 
```
- Then add this at the bottom
```

# Update, Upgrade an Clean Linux Every Sunday at 12:30 a.m.
30 0 * * 0 sudo nala update && sudo nala upgrade -y && sudo nala clean
```

---
## Installing SHELLGPT

- [SHELLGPT](https://github.com/dpd696/cheat-sheets/blob/98ea8c1400db7b4439bdde55972e66f9659c6be7/tools/shellgpt.md) - Guide for Installing SHELLGPT a ChatGPT for anything.

---