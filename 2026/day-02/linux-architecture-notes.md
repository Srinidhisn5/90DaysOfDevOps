# Linux Architecture, Processes, and systemd

## Linux Architecture
Linux mainly consists of:
- Kernel
- User Space
- systemd/init

### Kernel
- Core part of Linux
- Manages CPU, memory, processes, devices, and filesystem
- Acts as bridge between hardware and software

### User Space
- Area where users and applications run
- Examples: bash, vim, python

### systemd
- First process started during boot (PID 1)
- Manages services and background processes
- Helps monitor logs and restart services

Command used:
```bash
ps -p 1
```

---

## Linux Processes

- A process is a running program
- Every process has a PID (Process ID)

### Common Process States
- Running → actively using CPU
- Sleeping → waiting for event/input
- Stopped → paused process
- Zombie → completed but not cleaned properly

---

## Useful Linux Commands

```bash
ps
top
kill
systemctl
journalctl
```

- `ps` → shows running processes
- `top` → live system monitoring
- `kill` → terminate process using PID
- `systemctl` → manage services
- `journalctl` → view logs

---

## Why This Matters in DevOps

- Linux is used in most production servers
- Understanding processes helps in troubleshooting
- systemd helps manage services and logs
- Monitoring CPU and memory helps during incidents