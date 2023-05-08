# Mount

In **Linux ([[linux]])**, mount is a command in various operating systems. Before a user can access a file on a Unix-like machine, the file system on the device which contains the file needs to be mounted with the mount command. Frequently mount is used for SD card, USB storage, DVD and other removable storage devices. 

---
List mount-points
```
findmnt (optional)<device/directory>
```

Unmount
```
umount <device/directory>
```

## HOW TO MOUNT

- First, you need to install the NFS server on the machine that has the folder you want to share. You can do this by running the following command:
```
sudo apt-get install nfs-kernel-server
```
- Next, you need to configure the NFS server by editing the /etc/exports file. Add a line to the file that specifies the folder you want to share and the IP address of the machine that you want to grant access to. For example:
```
sudo nano /etc/exports
```
```
/path/to/folder 192.168.1.100(rw,sync,no_subtree_check)
```
- In this example, /path/to/folder is the path to the folder you want to share, and 192.168.1.100 is the IP address of the machine that you want to grant access to. The options "rw", "sync", and "no_subtree_check" specify the permissions and behavior of the shared folder.

- Save the /etc/exports file and restart the NFS server by running the following command:
```
sudo systemctl restart nfs-kernel-server
```
- On the machine that you want to access the shared folder from, you need to install the NFS client by running the following command:
```
sudo apt-get install nfs-common
```
- Then, you can mount the shared folder by running the following command:
```
sudo mount 192.168.1.101:/path/to/folder /mnt/shared
```
- In this example, 192.168.1.101 is the IP address of the machine that has the shared folder, and /mnt/shared is the local mount point where the shared folder will be accessible.

- Note that you may need to adjust firewall settings or network configurations to allow NFS traffic between the two machines.

## SYNOLOGY

- Showmount, called on the client machine, shows the share
```
showmount 10.0.0.100 -e
```
- Attach the NAS shared folder
```
sudo mount <nas.ip.address>:[/share/mount-path] [/mnt/point]
```
- Verify the mount was successful by checking the attached disks (df) and searching for the mount point we created on the Pi (grep /mnt/backups).
```
df -h | grep /mnt/backups
```
- If successful, it will return something like this: 
```
192.168.1.30:/volume1/backups  5.4T  3.7T  1.8T  68% /mnt/backups
```
