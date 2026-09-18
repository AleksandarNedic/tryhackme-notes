# Become a Hacker

## What is Hacking?

Hacking is the process of finding weaknesses in systems, applications, networks or devices and understanding how they can be exploited.

In cybersecurity, hacking is often performed legally to improve security.

---

## Ethical Hacking

**Ethical hacking** means testing systems with permission from the owner.

A security professional may:

* Find vulnerabilities
* Test whether vulnerabilities can be exploited
* Report the findings
* Help fix the vulnerabilities

Only test systems where you have permission.

---

## Common Areas of Cybersecurity

### Web Security

Testing websites and web applications for vulnerabilities.

Examples:

* SQL Injection
* XSS
* HTML Injection
* Authentication problems
* Access control problems

### Network Security

Understanding and testing network infrastructure.

Important concepts:

* IP addresses
* Ports
* Protocols
* TCP/UDP
* DNS
* Firewalls

### System Security

Testing operating systems and servers.

Examples:

* Linux
* Windows
* User permissions
* Services
* Privilege escalation

---

## Reconnaissance

Before attacking a target, a penetration tester usually gathers information about it.

This is called **reconnaissance**.

Example:

```text
Target
  ↓
Reconnaissance
  ↓
Enumeration
  ↓
Identify vulnerabilities
  ↓
Exploitation
  ↓
Privilege escalation
  ↓
Report
```

Tools I have used so far:

* **Nmap** → network/service enumeration
* **Gobuster** → web directory/file enumeration

---

## Enumeration

Enumeration means actively discovering information about a target.

For example:

```text
Nmap
↓
Open port 80
↓
Web server
↓
Gobuster
↓
Hidden directories/files
```

The goal is to understand the target's attack surface.

---

## Exploitation

If a vulnerability is discovered, a penetration tester may attempt to exploit it in a controlled and authorized environment.

Example:

```text
Vulnerability
      ↓
Exploitation
      ↓
Access
```

In TryHackMe, the target machines are intentionally designed for this type of practice.

---

## Privilege Escalation

Sometimes initial access only gives limited permissions.

The next goal may be to obtain higher privileges.

Example:

```text
Low-privileged user
       ↓
Privilege escalation
       ↓
Administrator / root
```

On Linux, `root` is the highest-privileged user.

---

## Tools

Tools help security professionals perform different tasks.

Examples:

```text
Nmap       → network reconnaissance
Gobuster   → web enumeration
Burp Suite → web application testing
Wireshark  → network traffic analysis
John       → password hash cracking
```

The important thing is understanding **what a tool does and why you are using it**, rather than memorizing commands.

---

## Learning Approach

Cybersecurity requires knowledge from several areas:

```text
Networking
    ↓
Linux / Windows
    ↓
Web
    ↓
Programming / Scripting
    ↓
Security Concepts
    ↓
Practical Labs
```

Practice platforms such as TryHackMe provide controlled environments where these concepts can be applied safely.

---

## Important Mindset

Becoming good at cybersecurity is not about memorizing hundreds of commands.

The important skills are:

* Understanding how systems work
* Knowing how to investigate a problem
* Reading documentation
* Understanding what tools are doing
* Thinking about how systems can fail
* Practicing in legal environments
* Learning from mistakes

## Key Things to Remember

**Reconnaissance** → gather information

**Enumeration** → discover services, files and other details

**Exploitation** → take advantage of a vulnerability

**Privilege escalation** → obtain higher privileges

**Ethical hacking** → hacking with authorization

**Nmap** → network/service enumeration

**Gobuster** → directory/file enumeration
