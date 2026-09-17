# TryHackMe — Pickle Rick

A beginner-friendly CTF room from TryHackMe focused on web enumeration, command execution, Linux enumeration and privilege escalation.

## What I Practiced

* Nmap reconnaissance
* Web enumeration
* `robots.txt`
* Linux file system enumeration
* Linux users and permissions
* Web command execution
* Understanding `www-data`
* `find`, `ls`, `strings` and other Linux commands
* `sudo` enumeration
* Privilege escalation
* Root access

## Attack Path

### 1. Reconnaissance

Started by scanning the target with Nmap to identify open ports and available services.

### 2. Web Enumeration

After discovering the web server, I inspected the website and found `robots.txt`.

This exposed information that helped me obtain the password for the Rick portal.

### 3. Command Panel

After logging into the portal, I discovered a command panel that allowed Linux commands to be executed on the target.

The commands were executed as:

```text
www-data
```

This was an important lesson because the web server was effectively giving me command execution on the machine.

### 4. Finding the Ingredients

I enumerated the filesystem and found the three required ingredients in different locations.

This required understanding Linux paths, file permissions and using commands such as:

```bash
ls
find
strings
```

### 5. Privilege Escalation

I checked the sudo permissions with:

```bash
sudo -l
```

The result showed that `www-data` could execute commands as any user without entering a password:

```text
(ALL) NOPASSWD: ALL
```

I verified the privilege escalation with:

```bash
sudo whoami
```

which returned:

```text
root
```

### 6. Root

With root privileges, I was able to access `/root` and locate the final ingredient.

## Key Lessons

The biggest things I learned from this room:

* A web application can provide command execution on the underlying Linux server.
* `www-data` is commonly used by web servers.
* Application-level command filtering is different from Linux file permissions.
* `find` is useful for locating files across a Linux filesystem.
* `sudo -l` is an important command when investigating privilege escalation.
* Misconfigured sudo permissions can allow a low-privileged user to become root.
* Enumeration is often more important than immediately trying random exploits.

## Skills

`Linux` `Nmap` `Web Enumeration` `Command Execution` `Privilege Escalation` `Sudo` `CTF`

## Platform

TryHackMe — Pickle Rick

Completed: September 2026
