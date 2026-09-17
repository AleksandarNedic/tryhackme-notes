# TryHackMe — Pickle Rick

## What I Practiced

* Nmap reconnaissance
* Gobuster directory enumeration
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

After discovering the web server, I used **Gobuster** to enumerate directories and files exposed by the web server.

I also inspected `robots.txt`, which contained information that helped me obtain the password for the Rick portal.

### 3. Command Panel

After logging into the portal, I discovered a command panel that allowed Linux commands to be executed on the target.

The commands were executed as:

```text
www-data
```

### 4. Finding the Ingredients

I enumerated the filesystem and found the three required ingredients in different locations.

I used Linux commands such as:

```bash
ls
find
strings
```

### 5. Privilege Escalation

I checked sudo permissions with:

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

With root privileges, I accessed `/root` and located the final ingredient.

## Key Lessons

* Nmap can be used for initial reconnaissance.
* Gobuster can enumerate directories and files on a web server.
* `robots.txt` can sometimes expose useful information.
* Web applications can provide command execution on the underlying server.
* `www-data` is commonly used by web servers.
* `sudo -l` can reveal dangerous sudo permissions.
* Misconfigured sudo permissions can allow privilege escalation to root.
* Linux enumeration is an important part of CTFs and penetration testing.
