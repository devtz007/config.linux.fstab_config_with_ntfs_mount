 
# /etc/fstab: Static File System Information

## 🌟 Overview 🌟
The `/etc/fstab` file is a static file system configuration file used by the mount command to automatically mount filesystems at boot time and other relevant system startup points. It contains entries for each filesystem that needs to be mounted and specifies the mount point, filesystem type, mount options, and other parameters.

## 🛠️ Structure 🛠️
Each line in `/etc/fstab` represents a separate filesystem entry and follows a specific format:

```plaintext
<file system> <mount point> <type> <options> <dump> <pass>
```

- **<file system>**: Specifies the block special device or remote filesystem to be mounted.
- **<mount point>**: Specifies the directory where the filesystem is to be mounted.
- **<type>**: Specifies the filesystem type (e.g., ext4, vfat, ntfs).
- **<options>**: Specifies mount options for the filesystem, separated by commas.
- **<dump>**: Used by the dump command to determine which filesystems need to be dumped.
- **<pass>**: Used by the fsck command to determine the order in which filesystem checks are done at boot time.

## 🌐 Linux File Systems 🌐

### 🟢 Boot 🟢
- **/boot/efi**
  ```plaintext
UUID=AB26-AB2F                                   /boot/efi    vfat   umask=0077,noatime,errors=remount-ro     0 1
  ```

### 🔵 Swap 🔵
- **Swap Partition**
  ```plaintext
UUID=3cc9ddee-50dc-4613-ace7-8c8b2feef3c9        none         swap   defaults
  ```

### ⚫ Root ⚫
- **/ (Root)**
  ```plaintext
UUID=c1e7003e-5dd0-4833-a2c7-c25cb547ef2d        /            ext4   noatime,errors=remount-ro                0 1
  ```


## 🌐 Windows File Systems 🌐

### 🟥 NTFS data partition 🟥
- **/media/us/part_1**
  ```plaintext
UUID=4CDDB17A08FB273C                            /media/u/pd20_others    ntfs3  nofail,uid=1000,gid=1000,windows_names,force   0 0
  ```


## 📝 Additional Notes 📝
- The `blkid` command can be used to retrieve UUIDs for devices.
- Care must be taken when modifying this file to avoid system instability or failure.
