# Linux Troubleshooting Runbook

## Target Service / Process
- Target service: cron

---

## Environment Basics

### Command
```bash
uname -a
```

Checked Linux kernel and system information.

### Command
```bash
cat /etc/os-release
```

Verified Linux distribution details.

---

## Filesystem Sanity Checks

### Command
```bash
mkdir /tmp/runbook-demo
```

Created temporary troubleshooting directory.

### Command
```bash
cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo
```

Verified file copy and directory contents.

---

## Snapshot: CPU & Memory

### Command
```bash
top
```

Observed running processes and CPU/memory usage.

### Command
```bash
free -h
```

Checked available and used system memory.

---

## Snapshot: Disk & IO

### Command
```bash
df -h
```

Checked disk space usage.

### Command
```bash
du -sh /var/log
```

Checked size of log directory.

---

## Snapshot: Network

### Command
```bash
ss -tulpn
```

Checked listening ports and active services.

### Command
```bash
curl -I https://google.com
```

Verified internet/network connectivity.

---

## Logs Reviewed

### Command
```bash
journalctl -u cron -n 20
```

Reviewed recent cron service logs.

### Command
```bash
tail -n 20 /var/log/syslog
```

Checked latest system log entries.

---

## Quick Findings

- System processes were running normally
- Memory and disk usage looked stable
- Cron service was active
- No major errors found in recent logs

---

## If This Worsens

- Restart affected service using `systemctl restart`
- Check detailed logs using `journalctl`
- Monitor CPU and memory usage continuously