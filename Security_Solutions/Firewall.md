## Firewall Types Made Easy to Remember

### 1. Stateless Firewall

**Think: Goldfish brain**

- Works at **Layer 3 and 4**
- Checks **each packet alone**
- Does **not remember past traffic**
- Fast but not smart

Example
If it blocks you once, it will still check your next packet like it never saw you before.

**Memory trick**
Stateless = No memory = Every packet is new

---

### 2. Stateful Firewall

**Think: Elephant memory**

- Works at **Layer 3 and 4**
- Tracks connections using a **state table**
- Remembers allowed and denied sessions
- More secure than stateless

Example
If a connection is allowed once, future packets are allowed automatically.

**Memory trick**
Stateful = Remembers connection state

---

### 3. Proxy Firewall

**Think: Security guard + translator**

- Works at **Layer 7**
- Acts as a **middleman**
- Inspects **packet content**
- Hides internal IP addresses
- Can block based on content

Example
User never talks directly to the internet. The proxy talks for them.

**Memory trick**
Proxy = Middleman + content inspection

---

### 4. Next Generation Firewall (NGFW)

**Think: Firewall on steroids**

- Works from **Layer 3 to 7**
- Deep packet inspection
- Built in **IPS**
- Can decrypt **SSL and TLS**
- Uses threat intelligence
- Detects attack patterns

**Memory trick**
NGFW = Stateful + Proxy + IPS + Intelligence

---

## Firewall Rule Components (Always Remember These)

Every firewall rule has:

- **Source IP** who sends
- **Destination IP** who receives
- **Port** where
- **Protocol** how TCP or UDP
- **Action** allow or deny
- **Direction** inbound or outbound

**Shortcut**
S D P P A D
Source Destination Port Protocol Action Direction

---

## Rule Directions Explained Simply

### Inbound Rules

Traffic coming **into** your system
Example
Allow HTTP port 80 to your web server

### Outbound Rules

Traffic going **out** of your system
Example
Block SMTP port 25 except mail server

### Forward Rules

Traffic passing **through** the firewall
Example
Forward port 80 traffic to internal web server

---

## Netfilter Explained Simply

**Netfilter** is the Linux firewall engine inside the kernel.

It handles:

- Packet filtering
- NAT
- Connection tracking

Tools built on Netfilter:

- **iptables** classic and powerful
- **nftables** modern replacement
- **firewalld** zone based and dynamic
- **ufw** beginner friendly frontend

---

## UFW Quick Guide

### Check firewall status

```
sudo ufw status
```

### Enable firewall

```
sudo ufw enable
```

### Disable firewall

```
sudo ufw disable
```

---

### Allow all outgoing traffic

```
sudo ufw default allow outgoing
```

Meaning
Everything can go out unless blocked later.

---

### Block incoming SSH

```
sudo ufw deny 22/tcp
```

Meaning
No one can SSH into your machine.

---

### List rules with numbers

```
sudo ufw status numbered
```

---

### Delete a rule

```
sudo ufw delete <rule_number>
```

Example

```
sudo ufw delete 2
```

---

## One Line Memory Summary

- Stateless = fast, no memory
- Stateful = remembers connections
- Proxy = content inspection
- NGFW = everything combined
- Netfilter = Linux firewall engine
- UFW = easy iptables
