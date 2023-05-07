# Getting System Hardware Information


## Displaying Full Hardware Information

```
lshw
lshw -short     # => short format
lshw -json      # => json format
lshw -html      # => html format
inxi -Fx
```

## Displaying Info About The CPU

```
lscpu
lshw -C cpu
lscpu -J    => json format
```

## Displaying Info About The Installed RAM Memory

```
dmidecode -t memory 
dmidecode -t memory | grep -i size
dmidecode -t memory | grep -i max
```

## Displaying Info About Free/Used Memory

```
free -m
```

## Getting Info About Pci Buses And About The Devices Connected To Them

```
lspci
lspci | grep -i wireless
lspci | grep -i vga
```

## Getting Info About USB Controllers And About Devices Connected

```
lsusb
lsusb -v
```

## Getting Info About Hard Disks

```
lshw -short -C disk
fdisk -l
fdisk -l /dev/sda
lsblk
hdparm -i /dev/sda
hdparm -I /dev/sda
```

## Benchmarking Disk Read Performance

```
hdparm -tT --direct /dev/sda
```

## Getting Info About WiFi Cards And Networks

```
lshw -C network
iw list
iwconfig
iwlist wlo1 scan
```

## Getting Hardware Information From The /proc Virtual fs

```
cat /proc/cpuinfo
/proc/partitions
cat /proc/meminfo
cat /proc/version
uname -r    # => kernel version
uname -a
acpi -bi    # battery information
acpi -V
```

# Working directly with device files (dd)

## Backing Up The MBR (the first sector of /dev/sda)

```
dd if=/dev/sda of=~/mbr.dat bs=512 count=1
```

## Restoring The MBR

```
dd if=~/mbr.dat of=/dev/sda bs=512 count=1
```

## Cloning A Partition (sda1 to sdb2)

```
dd if=/dev/sda1 of=/dev/sdb2 bs=4M status=progress
```