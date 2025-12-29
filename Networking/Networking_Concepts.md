# 🌐 OSI Model Cheat Sheet

**The OSI model has seven layers**

**Mnemonic:**
**Please Do Not Throw Sausage Pizza Away**

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

---

## 🧱 OSI Layers Explained

### Layer 1: Physical Layer

Responsible for physical transmission of data.

Examples:

- Ethernet cables
- Fiber optics
- WiFi radio signals
- 2.4 GHz, 5 GHz, 6 GHz bands
- Electrical and optical signals

---

### Layer 2: Data Link Layer

Enables data transfer between devices on the same network segment.

Examples:

- Ethernet (IEEE 802.3)
- WiFi (IEEE 802.11)
- MAC addresses
- ARP
- Switches

---

### Layer 3: Network Layer

Handles logical addressing and routing between networks.

Examples:

- IP
- ICMP
- IPSec
- VPN protocols

---

### Layer 4: Transport Layer

Provides end to end communication between applications on different hosts.

Examples:

- TCP
- UDP
- Ports

---

### Layer 5: Session Layer

Establishes, manages, and synchronizes communication sessions.

Examples:

- NFS
- RPC
- Session management and authentication

---

### Layer 6: Presentation Layer

Responsible for data format, encoding, compression, and encryption.

Examples:

- ASCII
- Unicode
- JPEG
- PNG
- Encryption formats

---

### Layer 7: Application Layer

Provides network services directly to user applications.

Examples:

- HTTP
- FTP
- DNS
- POP3
- SMTP
- IMAP
- SSH

---

## 📊 OSI Model Summary Table

| Layer | Name         | Main Function             | Examples       |
| ----- | ------------ | ------------------------- | -------------- |
| 7     | Application  | Services to applications  | HTTP, FTP, DNS |
| 6     | Presentation | Encoding, encryption      | Unicode, JPEG  |
| 5     | Session      | Session management        | NFS, RPC       |
| 4     | Transport    | End to end delivery       | TCP, UDP       |
| 3     | Network      | Routing and IP addressing | IP, ICMP       |
| 2     | Data Link    | Local delivery            | Ethernet, WiFi |
| 1     | Physical     | Signals and media         | Cables, radio  |

---

## 🧠 Hacker Focused One Line View

Think about what breaks at each layer.

- Application → Web apps, HTTP, DNS
- Presentation → Encryption, encoding
- Session → Authentication, sessions
- Transport → Ports, TCP vs UDP
- Network → IP, routing, firewalls
- Data Link → MAC, ARP, switches
- Physical → Cables, hardware

**Memory shortcut:**
**Web, Crypto, Login, Ports, IP, MAC, Wire**

---

## 🔄 TCP/IP vs OSI Model Mapping

| OSI Layer      | TCP/IP Layer | Example Protocols     |
| -------------- | ------------ | --------------------- |
| 7 Application  | Application  | HTTP, HTTPS, FTP, SSH |
| 6 Presentation | Application  | Encoding, encryption  |
| 5 Session      | Application  | Session control       |
| 4 Transport    | Transport    | TCP, UDP              |
| 3 Network      | Internet     | IP, ICMP, IPSec       |
| 2 Data Link    | Link         | Ethernet, WiFi        |
| 1 Physical     | Link         | Signals, media        |

---

## 🌍 IP Addressing Basics

- `.0` is the network address
- `.255` is the broadcast address

Example:

- `192.168.1.0` → network address
- `192.168.1.255` → broadcast address

Sending traffic to the broadcast address targets all hosts on the network.

---

## 🖥️ IP Commands

- Windows:

  ```
  ipconfig
  ```

- Linux:

  ```
  ifconfig
  ip address show
  ip a s
  ```

---

## 🔒 Private IP Ranges (RFC 1918)

- `10.0.0.0` to `10.255.255.255` (10/8)
- `172.16.0.0` to `172.31.255.255` (172.16/12)
- `192.168.0.0` to `192.168.255.255` (192.168/16)

---

## 📦 Encapsulation

Encapsulation is the process where each OSI layer adds its own header, and sometimes a trailer, before passing data to the layer below.

---

## 🌐 Common Network Services

- **TELNET**
  Remote terminal protocol.

- **Echo Server**
  Listens on port 7 and echoes received data.

- **Daytime Server**
  Listens on port 13 and returns the current date and time.

- **HTTP Server**
  Listens on TCP port 80 and serves web pages.
