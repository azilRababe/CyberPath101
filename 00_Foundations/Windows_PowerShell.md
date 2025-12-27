# ⚡ PowerShell Cheat Sheet

## 🔎 Command Discovery

- `Get-Command`
  Lists all available cmdlets, functions, aliases, and scripts.

- `Get-Command -CommandType Function`
  Filters commands by type, for example only functions.

---

## 📘 Help System

- `Get-Help`
  Displays help information for cmdlets.

  Common options:

  ```
  Get-Help Get-Date -Examples
  Get-Help Get-Date -Detailed
  Get-Help Get-Date -Full
  Get-Help Get-Date -Online
  ```

---

## 🔤 Aliases

- `Get-Alias`
  Lists all PowerShell aliases.

---

## 📦 Modules

- `Find-Module`
  Searches for modules in online repositories.

  Example:

  ```
  Find-Module -Name "PowerShell*"
  ```

- `Install-Module`
  Downloads and installs a module.

  Example:

  ```
  Install-Module -Name PowerShellGet
  ```

---

## 📂 File System Navigation

- `Get-ChildItem`
  Lists files and directories.

  Example:

  ```
  Get-ChildItem -Path .\Documents
  ```

- `Set-Location`
  Changes the current directory.

  Example:

  ```
  Set-Location -Path .\Documents
  ```

- `New-Item`
  Creates files or directories.

  Example:

  ```
  New-Item -Path ".\captain-cabin\captain-wardrobe" -ItemType Directory
  ```

- `Remove-Item`
  Deletes files or directories.

- `Copy-Item`
  Copies files or directories.

---

## 📄 File Content

- `Get-Content`
  Reads and displays file content.

- `Select-String`
  Searches for text inside files.

  Example:

  ```
  Select-String -Path ".\captain-hat.txt" -Pattern "hat"
  ```

  Note: `Select-String` supports regular expressions.

---

## 🔗 Piping and Filtering

- `|`
  Pipes output from one command to another.

- `Where-Object`
  Filters objects based on conditions.

  Example:

  ```
  Get-ChildItem | Where-Object Extension -eq ".txt"
  ```

### Comparison Operators

- `-eq` equal
- `-ne` not equal
- `-gt` greater than
- `-ge` greater than or equal
- `-lt` less than
- `-le` less than or equal
- `-like` pattern matching

---

## 🎯 Selecting Output

- `Select-Object`
  Selects specific properties or limits results.

  Example:

  ```
  Get-ChildItem | Select-Object Name, Length
  ```

---

## 🖥️ System Information

- `Get-ComputerInfo`
  Displays OS, hardware, BIOS, and system details.

- `Get-LocalUser`
  Lists local user accounts.

---

## 🌐 Network Information

- `Get-NetIPConfiguration`
  Shows network interface configuration.

- `Get-NetIPAddress`
  Lists all IP addresses, including inactive ones.

- `Get-NetTCPConnection`
  Displays active TCP connections.

---

## ⚙️ Processes and Services

- `Get-Process`
  Lists running processes with CPU and memory usage.

- `Get-Service`
  Displays services and their status.

---

## 🔐 Security and Integrity

- `Get-FileHash`
  Generates file hashes.

---

## 🌍 Remote Execution

- `Invoke-Command`
  Executes commands on remote systems.

  Example:

  ```
  Invoke-Command -ComputerName Server01 -ScriptBlock { Get-Process }
  ```

---

## ⭐ Pro Tips

- Always use `-Path` to specify exact locations.
- PowerShell works with objects, not plain text.
- Use `Get-Member` to inspect object properties:

  ```
  Get-Process | Get-Member
  ```
