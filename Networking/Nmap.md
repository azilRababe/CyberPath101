## 🛰️ Nmap Basics

**Nmap (Network Mapper)** is a free, open source tool used for network discovery and security auditing. It helps identify live hosts, open ports, running services, and operating systems.

---

## 🎯 Specifying Targets

Nmap supports multiple ways to define scan targets.

### IP Range

- Scan from `192.168.0.1` to `192.168.0.10`

```
192.168.0.1-10
```

### Subnet

- Scan an entire subnet

```
192.168.0.0/24
```

Equivalent to `192.168.0.0-255`

### Hostname

```
example.thm
```

---

## 🔍 Host Discovery

- `-sn`
  Discover live hosts only. No port scanning.

- `-sL`
  List targets without scanning them. Useful to verify scope.

Example:

```
nmap -sL 192.168.0.0/24
```

---

## 🚪 Port Scanning Techniques

- `-sT`
  TCP connect scan. Completes the full three way handshake.

- `-sS`
  TCP SYN scan. Sends only SYN packets. Stealthier and faster.

- `-sU`
  UDP scan for UDP services.

---

## 🔢 Port Selection

By default, Nmap scans the **top 1000 common ports**.

- `-F`
  Fast mode. Scans the top 100 ports.

- `-p10-1024`
  Scan ports 10 through 1024.

- `-p-25`
  Scan ports 1 through 25.

- `-p-`
  Scan all ports from 1 to 65535.

---

## 📌 Port Scan Options Summary

| Option      | Explanation        |
| ----------- | ------------------ |
| `-sT`       | TCP connect scan   |
| `-sS`       | TCP SYN scan       |
| `-sU`       | UDP scan           |
| `-F`        | Scan top 100 ports |
| `-p[range]` | Specify port range |
| `-p-`       | Scan all ports     |

---

## 🧠 OS and Service Detection

- `-O`
  Enable operating system detection.

- `-sV`
  Detect service versions running on open ports.

- `-A`
  Enables OS detection, version detection, and traceroute.

---

## 🚫 Skipping Host Discovery

- `-Pn`
  Treat all hosts as online and skip host discovery.

Useful when:

- ICMP is blocked
- Hosts appear down but are actually alive

---

## 🧾 Detection Options Summary

| Option | Explanation                   |
| ------ | ----------------------------- |
| `-O`   | OS detection                  |
| `-sV`  | Service and version detection |
| `-A`   | Aggressive scan               |
| `-Pn`  | Scan hosts that appear down   |

---

## ⏱️ Timing and Performance

Nmap timing templates control scan speed and stealth.

- `-T0` or `-T paranoid`
- `-T1` sneaky
- `-T2` polite
- `-T3` normal
- `-T4` aggressive
- `-T5` insane

Example:

```
nmap -T0 target
```

---

## ⚙️ Advanced Performance Tuning

- `--min-parallelism <num>`

- `--max-parallelism <num>`
  Control number of parallel probes.

- `--min-rate <number>`

- `--max-rate <number>`
  Control packet sending rate.

- `--host-timeout <time>`
  Maximum time to wait for a host.

---

## 🚀 Performance Options Summary

| Option              | Explanation                |
| ------------------- | -------------------------- |
| `-T0` to `-T5`      | Timing templates           |
| `--min-parallelism` | Minimum parallel probes    |
| `--max-parallelism` | Maximum parallel probes    |
| `--min-rate`        | Minimum packets per second |
| `--max-rate`        | Maximum packets per second |
| `--host-timeout`    | Maximum wait time per host |

---

## 📢 Verbosity and Debugging

- `-v`
  Enable verbose output.

- `-d`
  Debug output. Can be increased up to `-d9`.

---

## 💾 Output Formats

- `-oN <file>`
  Normal output.

- `-oX <file>`
  XML output.

- `-oG <file>`
  Grepable output. Useful for grep and awk.

- `-oA <basename>`
  Output in all major formats.

---

## 📄 Output Options Summary

| Option | Explanation     |
| ------ | --------------- |
| `-oN`  | Normal output   |
| `-oX`  | XML output      |
| `-oG`  | Grepable output |
| `-oA`  | All formats     |
