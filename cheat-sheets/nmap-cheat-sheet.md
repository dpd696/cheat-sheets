# Nmap Cheat Sheet 💻☠
===================

Contents
--------

### [Nmap Overview](#nmap_overview)

### [Nmap Help](#nmap_help)

### [Nmap Targeting](#nmap_targeting)

### [Nmap Scan Types](#nmap_scan_types)

### [Nmap Port Scanning](#nmap_port_scanning)

### [Nmap Timing Options](#nmap_timing_options)

### [Nmap Scripts](#nmap_scripts)

### [Extras & Additional Resources](#extras)

### [Credits](#credits)

Nmap overview: What is Nmap? Why is Nmap useful? {#nmap-overview-what-is-nmap-why-is-nmap-useful name="nmap_overview"}
------------------------------------------------

Nmap is an essential open-source tool for Ethical Hackers and
Penetration testers. It was initially created by [Gordon
Lyon](https://en.wikipedia.org/wiki/Gordon_Lyon) (aka Fyodor).
[Nmap](https://nmap.org) themselves do a great job describing the tool
(see below) and what is does, so why re-invent the wheel?

> Nmap (\"Network Mapper\") is a free and open source (license) utility
> for network discovery and security auditing. Many systems and network
> administrators also find it useful for tasks such as network
> inventory, managing service upgrade schedules, and monitoring host or
> service uptime. Nmap uses raw IP packets in novel ways to determine
> what hosts are available on the network, what services (application
> name and version) those hosts are offering, what operating systems
> (and OS versions) they are running, what type of packet
> filters/firewalls are in use, and dozens of other characteristics.

Want to see what an actual Nmap scan looks like and how to perform an
NMAP scan? Watch [this free
lesson](https://academy.zerotomastery.io/courses/complete-ethical-hacking-bootcamp-zero-to-mastery/lectures/25059762)
from the Zero To Mastery Ethical Hacking Bootcamp.

Nmap help {#nmap-help-1 name="nmap_help"}
---------

We can use \`nmap -h\` to display an extended help menu of Nmap. In this
extended help menu, you can find an overview of all possible options,
and which arguments some of them require in order to work. Note that you
can also use \`man npm\` for an in-depth manual about nmap.

Nmap targeting {#nmap-targeting-1 name="nmap_targeting"}
--------------

Nmap is an interesting tool that can be used in various ways. You can
scan one single target or multiple targets. Here is a list of examples,
showing the ways you can target something:

  **Command**                              **Description**
  ---------------------------------------- ---------------------------------
  `nmap 192.168.1.1`{.language-text}       Scanning a single IP
  `nmap www.domain.com`{.language-text}    Scanning a hostname
  `nmap 192.168.1.1-100`{.language-text}   Scanning an IP range
  `nmap 192.168.1.1/24`{.language-text}    Scanning a subnet
  `nmap -iL list.txt`{.language-text}      Scanning from a predefined list

Nmap scan types {#nmap-scan-types-1 name="nmap_scan_types"}
---------------

Besides the basic \`nmap \< target \>\`, we can also use various
scanning types in Nmap. Each of them has their own unique capabilities,
but also often come with the downside of one being noisier than the
other. Let us see which types we have:

  **Command**                               **Description**                                                                                                                                                                                                                                                                                                                                    **Root/Sudo required**   **Noise level**
  ----------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------ -----------------
  `nmap -sS <_target>`{.language-text}      This is a TCP SYN SCAN, also known as a stealth scan. This scan only sends a SYN packet and awaits a SYN/ACK response. When nmap receives a SYN/ACK on a specific probed port, it means the port exists on the machine and is open. This is a fast and pretty accurate scan, which you will use most of the time.                                  Required                 Very Low
  `nmap -sT <_target>`{.language-text}      The -sT scan is more accurate than a -sS scan, but the downside is that it is slower, makes more noise and easily detected by well set-up firewalls. This is because it makes a full three-way handshake (or better said, a full TCP connection) with the host.                                                                                    Not Required             Medium
  `nmap -sU <_target>`{.language-text}      This scan is used to scan for UDP ports. This is typically a slower and more difficult scan. Though most services use TCP, there are also services that use UDP, such as: DNS, SNMP, DHCP. So this scan is still useful as there are still exploitable UDP services. So don\'t make the mistake of skipping this scan, you might find something!   Required                 Medium
  `nmap -sn <_target(s)>`{.language-text}   This is a simple and fast ping scan to see which hosts reply to ICMP ping packets. This is useful if you are on the same (sub)network as the IP range you are scanning and if you only want to know which devices are live. You can also get the same result by using -Pn.                                                                         Not Required             Very Low
  `nmap -sV <_target>`{.language-text}      This is a service version scan. In order to know what exploits will work, it is very helpful to know the service version behind an open port. It might be that a certain exploit only works in one specific version of a certain service, as it might be patched in a new version.                                                                 Not Required             Medium
  `nmap -O <_target>`{.language-text}       This is a remote OS detection scan. We use this scan to learn what OS the target runs on. This is very useful as it gives an idea of what kind of exploits might work on the target, and which exploits won\'t work. Note that this scan only works if there is at least 1 open port and 1 closed port.                                            Required                 Medium
  `nmap -A <_target>`{.language-text}       This is an aggressive scan. This scan performs an OS detection, version detection, script scanning, and traceroute. Though it returns a lot of information, you will be alarming the target as this is probably the noisiest scan.                                                                                                                 Required                 Very High

Nmap port scanning {#nmap_port_scanning}
------------------

Sometimes you want to know if a certain port is open on a target, or
perhaps you want to know ALL open ports on the target. Luckily, Nmap
provides its users with ways to specify this:

  **Command**                                                                 **Description**
  --------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  `nmap -p <_port> <_target>`{.language-text}                                 Use -p \<\_port\> to scan for one specific port on the target.
  `nmap -p <_port_range_begin>-<_port_range_end> <_target>`{.language-text}   You can also use -p to scan for a range of ports, -p 1-20 \<\_target\> would scan for the ports 1 to 20 on the target.
  `nmap -p <_port_a>,<_port_b>,<_port_c> <_target>`{.language-text}           There is also the possibility to specify multiple specific ports by separating them with a comma.
  `nmap -p U:<_udp_port>,T:<_tcp_port> <_target>`{.language-text}             If you want to scan for both UDP and TCP ports, you can use U:\<\_udp\_port\> and T:\<\_tcp\_port\>, separated by a comma.
  `nmap -F <_target>`{.language-text}                                         The -F tells Nmap to scan for the 100 most common ports that can be open on a target.
  `nmap -top-ports <_amount> <_target>`{.language-text}                       With this option, you scan for the top \# ports, depending on what amount you provide.
  `nmap -p- <_target>`{.language-text}                                        This option tells Nmap to scan the target for all the known ports there are in the world\... there are 655,355 ports in total. This will clearly make the scan take longer to finish.

Nmap timing options {#”nmap_timing_options”}
-------------------

Nmap allows for the use of \"timing templates\", which allows the user
to specify how aggressive they wish to be with their scans, while
leaving Nmap to pick the exact timing values. There are 6 timing
templates:

  **Command**                            **Description**
  -------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  `nmap -T0 <_target>`{.language-text}   T0 is the slowest scan, also referred to as the \"Paranoid\" scan. This option is good for IDS evasion.
  `nmap -T1 <_target>`{.language-text}   T1 is an option faster then T0, but is still referred to as the \"Sneaky\" template. This timing option is also a good choice for IDS evasion.
  `nmap -T2 <_target>`{.language-text}   The T2 option is for a timely scan and is also known as the \"Polite\" timing option. This one slows the scan, which results in less bandwidth usage and less target machine resources
  `nmap -T3 <_target>`{.language-text}   T3 is also known as the default scan timer. Using this template would be the same as not using it at all. This is what Nmap uses by default when there is no template selected.
  `nmap -T4 <_target>`{.language-text}   T4 is an option to speed up scans by making the assumption that you are on a reasonably fast and reliable network. This time template is also referred to as the \"Aggressive\" template.
  `nmap -T5 <_target>`{.language-text}   T5 is an insanely fast mode, assuming that you are on an extraordinarily fast network\... or if you are willing to sacrifice some accuracy for speed. That is why it is also referred to as the \"Insane\" mode.

Nmap scripts {#nmap-scripts-1 name="nmap_scripts"}
------------

Last but not least\... Nmap provides us with scripts. These scripts come
in categories: - auth - broadcast - default. discovery - dos - exploit -
external - fuzzer - intrusive - malware - safe - version - vuln

We run a script in the following way:
`nmap --script <_script/_script_group> <_taget>`{.language-text}

Some scripts are very noisy, some not at all. Therefore, it is important
to read what each script does and if it is easily detectable by the
target or not.

Do note that you need to run `--script`{.language-text} scans as
root/sudo.

Extras & Additional Resources {#extras-additional-resources-1 name="extras"}
-----------------------------

When you are doing a pentest, it is useful to use the -oN option to
output your scan to a text file. This way, you can copy-paste it later
into your pentest report. Here is how to do it: \`nmap -oN
\<\_filename.txt\> \<\_target\>\`

You can also use multiple options in one scan. For example, this is
probably the most common scan you will perform:
`sudo nmap -sS <_target> -oN <_filename.txt>`{.language-text}

Lastly, we\'ve added some screenshots of various commands below.

**Want to dive deeper?**

-   Check out Gordon Lyon\'s [Nmap Network Scanning
    book](https://nmap.org/book)
-   Take the Zero To Mastery [Ethical Hacking
    Bootcamp](https://academy.zerotomastery.io/p/complete-ethical-hacking-bootcamp-zero-to-mastery)

#### `nmap 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - Basic nmap
command](//images.ctfassets.net/aq13lwl6616q/719xhAeZ1sPmOhe3QIcJT5/165a8c372961f31446da93355da09d7f/screenshot_basic_nmap_command.png)

#### `nmap -p 80 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - Specific port scan nmap
command](//images.ctfassets.net/aq13lwl6616q/LNcSKmNbozbUChRQMIoby/0b0f111cbd59887c058305ecc2d3168b/screenshot_specific_port_scan_nmap_command.png)

#### `nmap -p- 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - All known ports scan nmap
command](//images.ctfassets.net/aq13lwl6616q/5LxqaoYPAvnu9TtGqLrvdC/bf51aa25fea9b1d33bd54a6bbfdabfad/screenshot_all_known_ports_scan_nmap_command.png)

#### `sudo nmap -sV 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - Service scan nmap command
censored](//images.ctfassets.net/aq13lwl6616q/7t2VGpwJ3MwtXKzBBl8ORF/12e7a41a0bb3a9f2603f175d019ac93a/screenshot_service_scan_nmap_command_censored.png)

#### `nmap -T4 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - T4 nmap
command](//images.ctfassets.net/aq13lwl6616q/7GynCMqzUfNYKw1IWNsyvF/a6c2e358cdbd65b6365001d20f147bbf/screenshot_T4_nmap_command.png)

#### `sudo nmap -sS 192.168.0.239`{.language-text}

![\[ CHEAT-SHEET \] - Synscan nmap
command](//images.ctfassets.net/aq13lwl6616q/5wTUCA4Yd6Jth24b18s13s/cbac74e01852acc7edc3165e3d6dc92d/screenshot_synscan_nmap_command.png)

#### `nmap -sn 192.168.0.239`{.language-text}

[Back To Top](#contents)