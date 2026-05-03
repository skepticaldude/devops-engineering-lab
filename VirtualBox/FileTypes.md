# Linux File Types

In Linux, files are not just documents or images.  
Everything in Linux is treated as a file, including devices and communication channels.

You can identify file types using:

```bash
ls -l
```

The **first character** in the output shows the file type.

Example:

```text
-rw-r--r--   regular file
drwxr-xr-x   directory
lrwxrwxrwx   symbolic link
```

---

# Main Linux File Types

| Symbol | File Type | Description |
|--------|------------|-------------|
| `-` | Regular File | Normal files like text, images, videos, scripts |
| `d` | Directory | Folder containing other files |
| `l` | Symbolic Link | Shortcut/reference to another file |
| `c` | Character Device | Device handling data character-by-character |
| `b` | Block Device | Device handling data in blocks |
| `s` | Socket | Communication endpoint between processes |
| `p` | Named Pipe (FIFO) | One-way communication channel |

---

# 1. Regular File (`-`)

Normal files such as:

```bash
notes.txt
script.sh
photo.jpg
```

Example output:

```text
-rw-r--r--
```

---

# 2. Directory (`d`)

Folders used to organize files.

Examples:

```bash
/home
/etc
/var
```

Example output:

```text
drwxr-xr-x
```

---

# 3. Symbolic Link (`l`)

A shortcut pointing to another file or directory.

Example:

```text
lrwxrwxrwx link -> /etc/hosts
```

Create one with:

```bash
ln -s original_file link_name
```

---

# 4. Character Device (`c`)

Devices that process data one character at a time.

Examples:

```bash
/dev/null
/dev/tty
```

Example output:

```text
crw-rw-rw-
```

---

# 5. Block Device (`b`)

Storage devices that process data in blocks.

Examples:

```bash
/dev/sda
/dev/nvme0n1
```

Example output:

```text
brw-rw----
```

---

# 6. Socket (`s`)

Used for communication between processes.

Example:

```bash
/var/run/docker.sock
```

Example output:

```text
srw-rw----
```

Sockets may be:
- Local (Unix domain sockets)
- Network sockets (TCP/UDP)

---

# 7. Named Pipe / FIFO (`p`)

A special file used for one-way process communication.

Example output:

```text
prw-r--r--
```

Create one with:

```bash
mkfifo mypipe
```

---

# Useful Commands

View file types:

```bash
ls -l
```

View device files:

```bash
ls -l /dev
```

View Unix sockets:

```bash
ss -x
```

View network sockets:

```bash
ss -tulnp
```

---

# Quick Memory Guide

```text
-  Regular file
d  Directory
l  Symbolic link
c  Character device
b  Block device
s  Socket
p  Pipe (FIFO)
```
