# Services ⚙️

## 📚 Overview

Linux uses **systemd** to manage services and the system boot process. Services are background programs that provide functionality such as networking, SSH, web servers, and databases.

---

## 🧠 Key Concepts

- **Service** → A program running in the background that provides a specific function.
- **Daemon** → A background process, often ending with the letter **d** (e.g., `sshd`).
- **systemd** → The service manager and init system used by modern Linux distributions.
- **systemctl** → Command-line tool used to manage services.
- **Unit** → A resource managed by systemd (service, target, socket, mount, etc.).

---

## 💻 Essential Commands

| Command | Purpose |
|---------|---------|
| `systemctl status SERVICE` | Show service status |
| `systemctl start SERVICE` | Start a service |
| `systemctl stop SERVICE` | Stop a service |
| `systemctl restart SERVICE` | Restart a service |
| `systemctl reload SERVICE` | Reload configuration without restarting |
| `systemctl enable SERVICE` | Start service automatically at boot |
| `systemctl disable SERVICE` | Disable automatic startup |
| `systemctl is-active SERVICE` | Check if a service is running |
| `systemctl is-enabled SERVICE` | Check if a service starts at boot |
| `systemctl list-units --type=service` | List services |
| `journalctl -u SERVICE` | Show service logs |

---

## 🔍 Personal Notes

### 💡 Things I Learned

- Every **Service** is a **Process**, but not every Process is a Service.
- `systemd` is the first userspace process after the Linux kernel (**PID 1**).
- `systemctl` is used to control services managed by `systemd`.
- `start` runs a service immediately, while `enable` makes it start automatically after boot.
- `restart` stops and starts a service again, while `reload` only reloads its configuration.
- `journalctl` is the standard tool for viewing system and service logs.

---

### 🚧 Problems I Faced

#### I thought `enable` started a service immediately

At first, I assumed:

```bash
sudo systemctl enable nginx
```

would start the service.

I later learned that:

- `enable` only configures the service to start automatically after boot.
- `start` is required to run the service immediately.

---

## ⚠️ Common Mistakes

- Confusing `start` with `enable`
- Confusing `stop` with `disable`
- Using `restart` when `reload` is enough
- Assuming every background process is a Service
- Forgetting to check logs with `journalctl` when troubleshooting

---

## 💡 Interview Tips

Be able to explain:

- Service vs Process
- Daemon
- systemd vs systemctl
- start vs enable
- stop vs disable
- restart vs reload
- status vs is-active
- status vs is-enabled
- PID 1
- How to check service logs

---

## 📝 Summary

`systemd` is the standard service manager in modern Linux. Using `systemctl`, you can start, stop, restart, enable, disable, and monitor services.
