# Mount a Linux disk in WSL

- https://learn.microsoft.com/en-us/windows/wsl/wsl2-mount-disk

## PowerShell (Run as administrator)

```
GET-CimInstance -query "SELECT * from Win32_DiskDrive"
wsl --mount \\.\PHYSICALDRIVE2 --bare
wsl --unmount \\.\PHYSICALDRIVE2
```

## WSL shell

```
sudo lsblk
sudo mkdir /mnt/drive1
sudo mount /dev/sdd1 /mnt/drive1
```
