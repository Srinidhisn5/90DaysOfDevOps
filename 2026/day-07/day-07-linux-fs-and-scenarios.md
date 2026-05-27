# Linux File System Hierarchy & Scenario Practice

# Part 1 – Linux File System Hierarchy

## /

- Root directory of Linux filesystem
- Everything starts from `/`

Command:
```bash
ls -l /
```

I would use this when navigating the Linux filesystem.

---

## /home

- Stores user home directories
- Personal files and folders are stored here

Command:
```bash
ls -l /home
```

I would use this when accessing user files.

---

## /root

- Home directory of root user
- Accessible mainly using sudo/root privileges

Command:
```bash
sudo ls /root
```

I would use this when performing admin-level tasks.

---

## /etc

- Stores configuration files
- Important for system and service configs

Command:
```bash
ls -l /etc
```

I would use this when editing configuration files.

---

## /var/log

- Stores log files
- Very important for troubleshooting

Command:
```bash
ls -l /var/log
```

I would use this when checking service or system logs.

---

## /tmp

- Stores temporary files
- Files may be deleted after reboot

Command:
```bash
ls -l /tmp
```

I would use this for temporary testing files.

---

## /bin

- Contains essential Linux commands
- Example: ls, cp, mv

Command:
```bash
ls -l /bin
```

I would use this to understand where core commands are stored.

---

## /usr/bin

- Stores user command binaries
- Many installed programs exist here

Command:
```bash
ls -l /usr/bin
```

I would use this when checking installed command locations.

---

## /opt

- Stores optional or third-party applications

Command:
```bash
ls -l /opt
```

I would use this when installing external applications.

---

# Hands-on Practice

## Find largest log files

```bash
du -sh /var/log/* 2>/dev/null | sort -h | tail -5
```

Observed larger log files used by the system.

---

## Check hostname config

```bash
cat /etc/hostname
```

Displayed current system hostname.

---

## Check home directory

```bash
ls -la ~
```

Viewed hidden files and folders in home directory.

---

# Part 2 – Scenario-Based Practice

## Scenario 1 – Service Not Starting

### Step 1
```bash
systemctl status myapp
```

Why:
Check whether service is running, failed, or stopped.

### Step 2
```bash
journalctl -u myapp -n 50
```

Why:
Inspect recent logs related to the service.

### Step 3
```bash
systemctl is-enabled myapp
```

Why:
Verify whether service starts automatically on boot.

### Step 4
```bash
systemctl restart myapp
```

Why:
Attempt restarting the service after checking logs.

---

## Scenario 2 – High CPU Usage

### Step 1
```bash
top
```

Why:
Monitor live CPU and memory usage.

### Step 2
```bash
ps aux --sort=-%cpu | head -10
```

Why:
Identify top CPU-consuming processes.

### Step 3
```bash
ps -p <PID> -f
```

Why:
Inspect detailed process information.

---

## Scenario 3 – Finding Service Logs

### Step 1
```bash
systemctl status ssh
```

Why:
Check SSH service status.

### Step 2
```bash
journalctl -u ssh -n 50
```

Why:
View recent SSH logs.

### Step 3
```bash
journalctl -u ssh -f
```

Why:
Follow SSH logs in real-time.

---

## Scenario 4 – File Permission Issue

### Step 1
```bash
ls -l /home/user/backup.sh
```

Why:
Check current file permissions.

### Step 2
```bash
chmod +x /home/user/backup.sh
```

Why:
Add execute permission to script.

### Step 3
```bash
ls -l /home/user/backup.sh
```

Why:
Verify execute permission was added.

### Step 4
```bash
./backup.sh
```

Why:
Run the script after fixing permissions.