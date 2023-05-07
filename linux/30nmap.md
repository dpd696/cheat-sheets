# Scanning hosts and networks using nmap

## ** SCAN ONLY YOUR OWN HOSTS AND SERVERS !!! **
## Scanning Networks is your own responsibility
COMMAND | DESCRIPTION
---|---
nmap -sS 192.168.0.1 | Syn Scan - Half Open Scanning (root only)
nmap -sT 192.168.0.1 | Connect Scan
nmap -p- 192.168.0.1 | Scanning all ports (0-65535)
nmap -p 20,22-100,443,1000-2000 192.168.0.1 | Specifying the ports to scan
nmap -p 22,80 -sV 192.168.0.1 | Scan Version
nmap -sP 192.168.0.0/24 | Ping scanning (entire Network)
nmap -Pn 192.168.0.0/24 | Treat all hosts as online -- skip host discovery
nmap -sS 192.168.0.0/24 --exclude 192.168.0.10 | Excluding an IP
nmap -oN output.txt 192.168.0.1 | Saving the scanning report to a file
nmap -O 192.168.0.1 | OS Detection
nmap -A 192.168.0.1 | Enable OS detection, version detection, script scanning, and traceroute
nmap -p 80 -iL hosts.txt  | Reading The Targets From A File (ip/name/network separated by a new line or a whitespace)
nmap -n -iL hosts.txt -p 80 -oN output.txt | Exporting To Out Output File And Disabling Reverse DNS