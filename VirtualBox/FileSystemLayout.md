# Linux Filesystem & Command Cheat Sheet (Beginner → Sysadmin View)

---

# 1. `/` (Root Directory)

## Command
```bash
ls /


## Meaning

Lists everything in the **root directory**.

## Explanation

* `/` is the top of the Linux filesystem
* All directories start from here
* It is NOT inside any other folder

## Typical contents

```
bin  boot  dev  etc  home  usr  var  tmp
```

## Key idea

* `/` = root of everything (like the base of a tree)

---

# 2. `/bin`

## Command

```bash
ls /bin
```

## Meaning

Shows essential system commands.

## What it contains

Core Linux tools like:

```
ls, cp, mv, rm, cat, echo, mkdir, bash
```

## Purpose

* Basic user commands
* Required for system operation
* Available even in recovery mode

---

# 3. `/sbin`

## Command / tool example

```bash
/sbin/ifconfig
```

## Meaning

System administration binaries.

## What it contains

System-level tools like:

```
reboot, fsck, iptables, ifconfig
```

## Purpose

* Network configuration
* Disk repair
* System control
* Mostly used with root privileges

## Key idea

* `/bin` = normal tools
* `/sbin` = admin/system tools

---

# 4. `/usr`

## Command

```bash
ls /usr
```

## Meaning

User software and system resources.

## What it contains

```
bin, lib, share, local
```

## Purpose

* Installed applications
* Libraries
* Shared system resources

---

# 5. `/usr/share`

## Command

```bash
ls /usr/share
```

## Meaning

Shared application data (not executable programs).

## Contains

* documentation
* icons
* fonts
* translations (locales)
* application resources

## Key idea

* Programs live in `/usr/bin`
* Their resources live in `/usr/share`

---

# 6. `/var`

## Command

```bash
ls /var
```

## Meaning

Variable system data (changes frequently).

## Contains

```
log/  cache/  lib/  tmp/  spool/
```

## Purpose

* Logs
* Cached data
* Service activity
* System runtime data

---

# 7. `/var/log`

## Command

```bash
ls /var/log
```

## Meaning

System log files.

## Contains

```
syslog, auth.log, kern.log, boot.log
```

## Purpose

Used for:

* troubleshooting
* monitoring system activity
* security auditing

## Example

```bash
tail -f /var/log/syslog
```

---

# 8. `/tmp`

## Command

```bash
ls /tmp
```

## Meaning

Temporary files directory.

## Contains

* installer files
* cache data
* crash leftovers
* script temp files

## Purpose

* short-term storage for applications
* automatically cleaned often

## Key idea

* NOT permanent storage
* safe to clear carefully

---

# 9. Cleaning `/tmp`

## Safe method

```bash
sudo systemd-tmpfiles --clean
```

## Reboot method

```bash
sudo reboot
```

## Manual (risky)

```bash
sudo rm -rf /tmp/*
```

## Important warning

* may affect running programs
* should be done carefully

---

# 10. `/boot`

## Command

```bash
ls /boot
```

## Meaning

Boot system files.

## Contains

* Linux kernel (`vmlinuz`)
* initramfs
* GRUB configuration

## Purpose

* system startup files
* required for booting Linux

---

# 11. GRUB vs LILO

## GRUB (modern bootloader)

* flexible
* supports multiple OS
* has boot menu
* widely used today

## LILO (legacy bootloader)

* older system
* simpler design
* requires reinstall after changes
* mostly deprecated

---

# 12. `/bin` vs `/sbin`

| Feature  | `/bin`         | `/sbin`        |
| -------- | -------------- | -------------- |
| Users    | everyone       | admin/root     |
| Purpose  | basic commands | system control |
| Examples | ls, cp, cat    | reboot, fsck   |

---

# 13. `ls` vs `ls /`

## `ls`

```bash
ls
```

* lists current directory

## `ls /`

```bash
ls /
```

* lists root directory

## Difference

| Command | Scope            |
| ------- | ---------------- |
| `ls`    | current location |
| `ls /`  | system root      |

---

# 14. `/tmp` highlighting (why it appears colored)

## Reason

* terminal color rules (`ls --color`)
* sticky bit permissions
* system sensitivity (temporary files)

## Permission example

```
drwxrwxrwt
```

## Meaning

* users can write files
* cannot delete others’ files

---

# 15. Key Linux Structure Summary

| Directory    | Purpose              |
| ------------ | -------------------- |
| `/`          | root of system       |
| `/bin`       | essential commands   |
| `/sbin`      | system admin tools   |
| `/usr`       | installed software   |
| `/usr/share` | shared app data      |
| `/var`       | changing system data |
| `/var/log`   | system logs          |
| `/tmp`       | temporary files      |
| `/boot`      | startup system files |

---

# Core Concept

Linux is structured as a hierarchy where:

* `/` = foundation
* each directory has a specific system role
* sysadmins focus on `/etc`, `/var`, `/boot`, `/tmp`
* users mainly interact with `/home` and `/usr`

```
```
