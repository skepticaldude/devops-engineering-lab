# Linux Notes — Processes, Daemons, `/proc`, Directories & Terminal Basics

## Daemons

A **daemon** is a background process that runs continuously on a Linux/Unix system and performs services without direct user interaction.

### Characteristics
- Runs in the background
- Usually starts automatically during boot
- Waits for requests/events
- Often ends with `d`

### Examples
- `sshd` → SSH server daemon
- `systemd` → system/service manager
- `crond` → scheduled task daemon
- `avahi-daemon` → local network discovery

### Useful Commands
```bash
ps aux
systemctl list-units --type=service
```

---

# The `/proc` File System

`/proc` is a **virtual file system** that provides information about:
- running processes
- system memory
- CPU
- kernel information

It is generated dynamically by the kernel.

### Examples
```bash
cat /proc/cpuinfo
cat /proc/meminfo
```

### Process-specific info
Each running process has a PID folder:
```bash
/proc/<PID>
```

Example:
```bash
cat /proc/1234/status
```

---

# Avahi Daemon

`avahi-daemon` is used for:
- local network discovery
- mDNS/DNS-SD
- finding printers/devices automatically

### Safe actions
- Reading files
- Viewing process information

### Risky actions
- Killing the daemon
- Disabling the service
- Editing configs without understanding them

### Restart command
```bash
sudo systemctl restart avahi-daemon
```

---

# Linux Directories

## `/bin`

Contains essential user commands.

### Examples
```bash
ls
cp
mv
cat
bash
```

View contents:
```bash
ls /bin
```

---

## `/sbin`

Contains system administration commands.

### Examples
```bash
reboot
shutdown
fsck
iptables
```

View contents:
```bash
ls /sbin
```

---

## Difference Between `/bin` and `/sbin`

| Directory | Purpose | Typical User |
|---|---|---|
| `/bin` | Basic user commands | All users |
| `/sbin` | System/admin commands | Root/admin |

---

# SSH Directory

View SSH configuration files:
```bash
ls /etc/ssh
```

### Common Files
| File | Purpose |
|---|---|
| `ssh_config` | Client SSH config |
| `sshd_config` | SSH server config |
| `ssh_host_*` | Host identity keys |

---

# Piping (`|`)

A pipe sends the output of one command into another command.

### Example
```bash
ls /bin | less
```

This sends the output of `ls /bin` into `less`.

---

# `less`

`less` is a pager program used to view long outputs page-by-page.

### Common Controls
| Key | Action |
|---|---|
| `Space` | Next page |
| `b` | Previous page |
| `/word` | Search |
| `n` | Next result |
| `q` | Quit |

### Examples
```bash
ps aux | less
cat file.txt | less
```

---

# `more`

`more` is an older pager program similar to `less`.

### Example
```bash
ls /bin | more
```

### Common Controls
| Key | Action |
|---|---|
| `Space` | Next page |
| `Enter` | Next line |
| `q` | Quit |

---

# Difference Between `more` and `less`

| Feature | `more` | `less` |
|---|---|---|
| Forward scrolling | Yes | Yes |
| Backward scrolling | Limited | Yes |
| Search | Basic | Advanced |
| Navigation | Simple | Better |

---

# The `-h` Flag

`-h` commonly means:
1. help
2. human-readable output

---

## Help Example
```bash
command -h
command --help
```

---

## Human-readable Example
```bash
ls -lh
df -h
```

### Without `-h`
```text
1048576
```

### With `-h`
```text
1.0M
```

---

# Colored Terminal Output

## Enable colored `ls`
```bash
alias ls='ls --color=auto'
```

Add permanently:
```bash
echo "alias ls='ls --color=auto'" >> ~/.bashrc
source ~/.bashrc
```

---

## Test terminal colors
```bash
echo -e "\e[31mThis is red text\e[0m"
```

---

# Useful Linux Commands Learned

```bash
ps aux
ls /bin
ls /sbin
ls /etc/ssh
cat /proc/cpuinfo
systemctl list-units --type=service
df -h
ls -lh
```
