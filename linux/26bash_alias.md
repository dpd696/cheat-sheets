# Alias

---
## Create Aliases to Perform Tasks by Shortcut Name

```
nano ~/.bashrc
```

---
- Common Alias Commands to Add at the End of ~/.bashrc
```
alias c="clear"
alias cl="clear;ls;pwd"
alias root="sudo su"
alias ports="netstat -tupan"
alias sshconfig="sudo vim /etc/ssh/sshd_config"
alias update="sudo apt update && sudo apt dist-upgrade -y && sudo apt clean"
alias lt="ls -hSF --size -1"
alias ping='ping -c 5'
alias now="date +%F\ %T"
alias cp="cp -i"
alias mv="mv -i"
alias rm="rm -i"
alias nano="nano -l"
alias sudo='sudo '
```
- Setup Alias to Connect SSH
```
alias kali="ssh -p 22 -l username 10.0.0.0"
```