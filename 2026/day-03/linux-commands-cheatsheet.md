# 🐧 Linux Command Cheat Sheet
> Your reusable toolkit for Process Management, File System & Networking

---

## ⚙️ Process Management

| Command | Usage |
|---------|-------|
| `ps aux` | List all running processes |
| `top` | Real-time process viewer |
| `htop` | Enhanced interactive process viewer |
| `pidof <name>` | Get PID of a process by name |
| `kill <PID>` | Terminate process by PID |
| `kill -9 <PID>` | Force kill a process immediately |
| `pkill <name>` | Kill processes by name |
| `bg` | Resume a stopped job in background |
| `fg` | Bring background job to foreground |
| `jobs` | List all active shell jobs |
| `nice -n 10 <cmd>` | Start process with lower priority |
| `renice -n 5 -p <PID>` | Change priority of running process |
| `uptime` | Show system uptime and load average |

---

## 📁 File System

| Command | Usage |
|---------|-------|
| `ls -lah` | List files — long format, human readable |
| `cd <dir>` | Change to directory |
| `pwd` | Print current working directory |
| `mkdir -p <dir>` | Create directory and parents if needed |
| `rm -rf <dir>` | Remove directory and contents recursively |
| `cp -r <src> <dest>` | Copy files or directories recursively |
| `mv <src> <dest>` | Move or rename files |
| `touch <file>` | Create an empty file |
| `cat <file>` | Display file contents |
| `less <file>` | Scroll through file page-by-page |
| `head -n 20 <file>` | Show first 20 lines of a file |
| `tail -f <file>` | Follow and stream live file updates |
| `find /path -name <file>` | Search for file by name |
| `du -sh <dir>` | Show total size of a directory |
| `df -h` | Show disk space usage on all mounts |
| `chmod +x <file>` | Make a file executable |
| `chown user:group <file>` | Change file owner and group |

---

## 🌐 Networking Troubleshooting

| Command | Usage |
|---------|-------|
| `ip addr` | Show all IP addresses and interfaces |
| `ping <host>` | Test basic network connectivity |
| `curl -I <url>` | Fetch HTTP response headers only |
| `dig <domain>` | Perform a DNS lookup |
| `ss -tulnp` | Show all listening ports and services |
| `netstat -tulnp` | Network connections — legacy alternative |
| `traceroute <host>` | Trace the packet route to a host |
| `hostname -I` | Show local machine IP address |
| `wget <url>` | Download a file from the internet |
| `nc -zv <host> <port>` | Test if a port is open on a host |

---

## 🔥 Pro Tip One-Liners

```bash
# Find a specific running process
ps aux | grep <process_name>

# Monitor system logs in real time
tail -f /var/log/syslog

# Sort directories by size (largest last)
du -sh * | sort -h

# Show a specific network interface
ip addr show eth0

# Get your public IP address
curl ifconfig.me

# Kill process by name instantly
pkill -9 <process_name>

# Find which process is using a port
ss -tulnp | grep <port>
