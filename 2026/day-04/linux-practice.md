# Linux Practice – Processes and Services

## Process Checks

### Command
```bash
ps aux | head
```

Observed running Linux processes and basic CPU/memory usage.

### Command
```bash
top
```

Monitored live running processes and system resource usage.

---

## Service Checks

### Command
```bash
systemctl status cron
```

Checked cron service status and verified service information.

### Command
```bash
systemctl list-units --type=service
```

Listed available system services.

---

## Log Checks

### Command
```bash
journalctl -u cron -n 20
```

Viewed recent logs related to cron service.

### Command
```bash
tail -n 20 /var/log/syslog
```

Checked recent system log entries.

---

## Mini Troubleshooting Steps

- Used `ps aux` to inspect running processes
- Used `top` to monitor system activity
- Checked cron service status using `systemctl`
- Reviewed logs using `journalctl` and `tail`
- Verified that the service was running correctly