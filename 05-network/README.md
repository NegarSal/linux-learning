# Network 🌐

## 📚 Overview

Linux networking enables computers to communicate with each other and the Internet. Understanding basic networking concepts is essential for system administration and troubleshooting.

---

## 🧠 Key Concepts

- **Hostname** → Computer name
- **IP Address** → Network address of a device
- **IPv4** → 32-bit IP address
- **IPv6** → 128-bit IP address
- **DNS** → Resolves domain names to IP addresses
- **Gateway** → Connects a local network to other networks
- **Loopback** → Internal interface (`127.0.0.1`)
- **Localhost** → Hostname that resolves to `127.0.0.1`
- **Network Interface** → Hardware or virtual network adapter

---

## 💻 Essential Commands

| Command | Purpose |
|---------|---------|
| `hostname` | Show hostname |
| `hostnamectl` | Show or change hostname |
| `ip a` | Show IP addresses |
| `ip link` | Show network interfaces |
| `ip route` | Show routing table |
| `ping` | Test network connectivity |
| `ss -tuln` | Show listening ports |
| `curl` | Retrieve data from a server |
| `wget` | Download files |

---

## 🔍 Personal Notes

### 💡 Things I Learned

- `hostnamectl` provides much more information than `hostname`.
- `ip` is the modern replacement for the old `ifconfig`.
- `ss -tuln` is my quick command for checking listening services.

| Option | Meaning |
|--------|---------|
| `t` | TCP |
| `u` | UDP |
| `l` | Listening |
| `n` | Numeric output |

Easy way to remember:

```text
t = TCP
u = UDP
l = Listening
n = Numeric
```

### 🚧 Problems I Faced

#### DNS vs Internet

During `git push` I received:

```text
Temporary failure in name resolution
```

The problem was not Git or GitHub. It was caused by Internet/DNS connectivity, so the system could not resolve `github.com` to an IP address.

---

## ⚠️ Common Mistakes

- Confusing Hostname with IP Address
- Assuming `localhost` is the same as the network IP
- Assuming a successful `ping` means a web service is working
- Forgetting that DNS is required when using domain names

---

## 💡 Interview Tips

Be able to explain:

- Hostname vs IP Address
- IPv4 vs IPv6
- Public IP vs Private IP
- DNS
- Gateway

---

## 📝 Summary

Linux networking is based on hostnames, IP addresses, DNS, gateways, and network interfaces. Commands like `ip`, `ping`, `curl`, `wget`, and `ss` are essential for troubleshooting and managing network connectivity.
