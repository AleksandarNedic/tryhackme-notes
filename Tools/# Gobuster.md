# Gobuster

## What is Gobuster?

Gobuster is a tool used for **enumeration**.

It can be used to discover things such as:

* Hidden directories
* Files
* Subdomains
* Virtual hosts

In web penetration testing, it is commonly used to discover parts of a website that are not linked from the main page.

---

## Directory Enumeration

The basic command is:

```bash
gobuster dir -u http://<IP> -w <wordlist>
```

Example:

```bash
gobuster dir -u http://10.10.10.10 -w /usr/share/wordlists/dirb/common.txt
```

### What do the options mean?

```text
dir
```

Tells Gobuster to perform **directory/file enumeration**.

```text
-u
```

Specifies the target URL.

```text
-w
```

Specifies the **wordlist** that Gobuster will use.

The wordlist contains possible directory and file names that Gobuster tests against the website.

---

## Example

If the wordlist contains:

```text
admin
login
robots.txt
backup
uploads
```

Gobuster will make requests such as:

```text
http://target/admin
http://target/login
http://target/robots.txt
http://target/backup
http://target/uploads
```

If something exists, Gobuster can report it.

Example:

```text
/admin        (Status: 301)
/robots.txt   (Status: 200)
/uploads      (Status: 301)
```

---

## Gobuster in a CTF

A common workflow is:

```text
Nmap
  ↓
Find web server
  ↓
Gobuster
  ↓
Find directories/files
  ↓
Investigate what you found
```

In the **Pickle Rick** room, I used Gobuster for web enumeration to discover files and directories that could provide useful information.

---

## Important Things to Remember

* Gobuster is an **enumeration tool**, not an automatic hacking tool.
* It works by testing many possible paths from a wordlist.
* `dir` is used for directory/file enumeration.
* `-u` specifies the target.
* `-w` specifies the wordlist.
* Finding something with Gobuster doesn't mean it is vulnerable — it means **you found something worth investigating**.

## Basic Command to Remember

```bash
gobuster dir -u <URL> -w <WORDLIST>
```
