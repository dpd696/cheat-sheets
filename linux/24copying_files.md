# Copying files using SCP and RSYNC

---
# SCP

## Copying A Local File To A Remote Destination

```
scp a.txt john@80.0.0.1:~
scp -P 2288 a.txt john@80.0.0.1:~       # using a custom port
```

---
## Copying A Local File From A Remote Destination To The Current Directory

```
scp -P 2290 john@80.0.0.1:~/a.txt .
```

---
## Copying A Local Directory To A Remote Destination (-r)

```
scp -P 2290 -r projects/ john@80.0.0.1:~
```

---
# RSYNC

## Synchronizing A Directory

```
sudo rsync -av /etc/ ~/etc-backup/
```

---
## Mirroring (Deleting From Destination The Files That Were Deleting From Source)

```
sudo rsync -av --delete /etc/ ~/etc-backup/
```

---
## Excluding Files

```
rsync -av --exclude-from='~/exclude.txt' source_directory/ destination_directory/
```
- exclude.txt:
- *.avi
- music/
- abc.mkv
```
rsync -av --exclude='*.mkv' --exclude='movie1.avi' source_directory/ destination_directory/
```

---
## Synchronizing A Directory Over The Network Using SSH

```
sudo rsync -av -e ssh /etc/ student@192.168.0.108:~/etc-backup/ 
```

---
## Using A Custom Port

```
sudo rsync -av -e 'ssh -p 2267' /etc/ student@192.168.0.108:~/etc-backup/ 
```