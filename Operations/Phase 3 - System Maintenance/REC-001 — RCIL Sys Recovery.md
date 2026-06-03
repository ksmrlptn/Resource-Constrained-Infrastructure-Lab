## Purpose

This document defines the operational procedure for creating and maintaining a recovery backup for the RCIL infrastructure environment. It ensures the system can be restored after failure, corruption, or full reinstallation.

![[Snapshot_2026-05-25_15-57-15.png]]


## Scope

This procedure covers:
- installed package list backup
- system configuration backup
- recovery kit creation
- external USB storage transfer

It does not include full disk imaging or automated backup systems.



## Recovery Kit Overview

The recovery kit is stored externally on a USB flash drive under:

```
/files/recovery-kit/
```

It is designed to be independent of the primary system disk.



## Recovery Kit Contents

- `pkglist.txt`  
  List of installed Arch Linux packages

- `system-configs.tar.gz`  
  Archive of system configuration files from `/etc`

- `README.md`  
  Recovery instructions and restore guide



## Backup Procedure

### 1. Create recovery directory
```bash
mkdir -p ~/recovery-kit
```

### 2. Export installed package list
```bash
pacman -Qqe > ~/recovery-kit/pkglist.txt
```

### 3. Create system configuration backup
```bash
sudo tar -czf ~/recovery-kit/system-configs.tar.gz /etc
```

### 4. Mount external USB storage
```bash
sudo mount /dev/sdb1 /mnt/usb
```

### 5. Copy recovery kit to USB
```bash
sudo cp -r ~/recovery-kit /mnt/usb/files/
```

### 6. Safely unmount USB
```bash
sudo umount /mnt/usb
```

### Verification Steps
```bash
ls -lh ~/recovery-kit
ls -lh /mnt/usb/files/recovery-kit
```
