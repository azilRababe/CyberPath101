# 🧾 Windows Command Line Cheat Sheet (CMD)

## 🔍 System Information

- `ver`
  Displays the operating system version.

- `systeminfo`
  Shows detailed system information like OS, CPU, memory, and patches.

- `set`
  Displays environment variables, including the PATH.
  Example:

  ```
  PATH=...
  ```

---

## 🖥️ Screen and Help

- `cls`
  Clears the Command Prompt screen.

- `help`
  Displays general help or help for a specific command.
  Example:

  ```
  help dir
  ```

- `command /?`
  Shows help for a specific command.
  Example:

  ```
  tasklist /?
  ```

---

## 📂 Directory Navigation

- `cd`
  Displays the current drive and directory.

- `cd <directory>`
  Changes to the specified directory.

- `cd ..`
  Moves up one directory level.

- `dir`
  Lists files and directories in the current directory.

  Useful options:

  - `dir /a` → shows hidden and system files
  - `dir /s` → lists files in all subdirectories

- `tree`
  Displays directory structure visually.

---

## 📁 File and Directory Management

- `mkdir <directory_name>`
  Creates a new directory.

- `rmdir <directory_name>`
  Deletes a directory.

- `copy <source> <destination>`
  Copies files.

- `move <source> <destination>`
  Moves files.

- `del` or `erase`
  Deletes files.

- `type <file>`
  Displays the content of a text file.

---

## 📄 Viewing Long Output

- `more <file>`
  Displays a text file page by page.

- `<command> | more`
  Pipes long output to view it page by page.
  Example:

  ```
  driverquery | more
  ```

---

## 🌐 Network Commands

- `ipconfig`
  Displays basic network information.

- `ipconfig /all`
  Shows detailed network configuration.

- `ping <target>`
  Checks connectivity to another host.

- `tracert <target>`
  Traces the route packets take to reach a destination.

- `nslookup <domain>`
  Resolves a domain name to an IP address.

  Example using a specific DNS server:

  ```
  nslookup example.com 1.1.1.1
  ```

- `netstat`
  Displays active network connections and listening ports.

---

## ⚙️ Process and Task Management

- `tasklist`
  Lists running processes.

- `tasklist /FI "imagename eq sshd.exe"`
  Filters processes by image name.

- `taskkill /PID <pid>`
  Terminates a process by PID.

---

## 🧠 Disk and System Maintenance

- `chkdsk`
  Checks disk for errors and bad sectors.

- `driverquery`
  Lists installed device drivers.

- `sfc /scannow`
  Scans and repairs corrupted system files.

---

## ⭐ Pro Tip: Wildcards

- `*` can match multiple files.

  Example:

  ```
  copy *.md C:\Markdown
  ```

  This copies all `.md` files to `C:\Markdown`.
