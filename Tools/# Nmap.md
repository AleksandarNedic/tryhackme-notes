# Nmap

## What is Nmap?

Nmap (Network Mapper) is a tool used for **network discovery and security auditing**.

It can help identify:

* Which ports are open
* Which services are running
* Which ports are closed or filtered
* What operating system a target may be using
* Service and version information

In penetration testing, Nmap is often used during the **reconnaissance/enumeration** phase.

---

## Basic Scan

```bash
nmap <IP>
```

Example:

```bash
nmap 10.10.10.10
```

This performs a basic scan of common TCP ports.

---

## What is a Port?

A port identifies a specific network service on a device.

Common examples:

```text
22   SSH
80   HTTP
443  HTTPS
21   FTP
25   SMTP
53   DNS
```

If Nmap reports:

```text
80/tcp open http
```

it means:

* `80` → port number
* `tcp` → protocol
* `open` → the port is accepting connections
* `http` → Nmap identified HTTP running there

---

## Service and Version Detection

```bash
nmap -sV <IP>
```

This attempts to determine the **service and its version** running on open ports.

Example:

```text
80/tcp open  http  Apache httpd 2.4.18
```

This can be useful because knowing the exact service/version can help identify potential vulnerabilities.

---

## Scan All TCP Ports

```bash
nmap -p- <IP>
```

Instead of scanning only the most common ports, this scans ports **1–65535**.

Useful when you don't want to miss a service running on an unusual port.

---

## Specific Ports

```bash
nmap -p 22,80,443 <IP>
```

Scans only the specified ports.

You can also specify a range:

```bash
nmap -p 1-1000 <IP>
```

---

## OS Detection

```bash
nmap -O <IP>
```

Attempts to identify the target's operating system.

Results are not always accurate, especially when the target is behind filtering or other network configurations.

---

## Useful Scan

A common enumeration scan is:

```bash
nmap -sV -O <IP>
```

This combines:

* Service/version detection
* OS detection

---

## Nmap in a CTF

A typical workflow can look like:

```text
Target IP
   ↓
Nmap
   ↓
Open ports
   ↓
Identify services
   ↓
Enumerate those services
   ↓
Look for vulnerabilities / attack surface
```

For example:

```text
80/tcp open http
```

would tell me that I should investigate the web server next.

In the **Pickle Rick** room, Nmap was part of the initial reconnaissance before moving on to web enumeration with Gobuster.

---

## Important Commands

| Command               | Purpose                   |
| --------------------- | ------------------------- |
| `nmap <IP>`           | Basic scan                |
| `nmap -sV <IP>`       | Service/version detection |
| `nmap -p- <IP>`       | Scan all TCP ports        |
| `nmap -p 22,80 <IP>`  | Scan specific ports       |
| `nmap -p 1-1000 <IP>` | Scan a port range         |
| `nmap -O <IP>`        | OS detection              |
| `nmap -sV -O <IP>`    | Service + OS detection    |

## Key Things I Learned

* Nmap is primarily a **reconnaissance/enumeration tool**.
* An open port usually means there is a service listening there.
* The port number alone doesn't guarantee which service is actually running.
* `-sV` helps identify the service and version.
* `-p-` scans all TCP ports.
* Finding an open port is usually the beginning of investigation, not the end.
