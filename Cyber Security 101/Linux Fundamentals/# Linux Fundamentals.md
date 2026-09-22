# Linux Fundamentals

Personal notes from learning Linux fundamentals through TryHackMe.

---

## 1. Linux Basics

### Navigation

```bash
pwd
```

Shows the current working directory.

```bash
ls
```

Lists files and directories.

```bash
ls -la
```

Lists all files, including hidden files, with detailed information.

```bash
cd directory
```

Changes the current directory.

```bash
cd ..
```

Moves one directory up.

```bash
cd ~
```

Moves to the current user's home directory.

---

### Files and Directories

```bash
cat file.txt
```

Displays the contents of a file.

```bash
less file.txt
```

Opens a file for easier viewing.

Press `q` to exit `less`.

```bash
touch file.txt
```

Creates an empty file.

```bash
mkdir folder
```

Creates a directory.

```bash
cp file.txt backup.txt
```

Copies a file.

```bash
mv file.txt folder/
```

Moves a file.

```bash
rm file.txt
```

Removes a file.

```bash
rmdir folder
```

Removes an empty directory.

---

### Hidden Files

Linux files beginning with `.` are hidden.

Example:

```text
.flag.txt
```

To see hidden files:

```bash
ls -la
```

---

### Searching

```bash
find / -type f -name "file.txt" 2>/dev/null
```

Searches the filesystem for a file.

`2>/dev/null` hides error messages such as permission errors.

Example:

```bash
find / -type f -iname "*access*log*" 2>/dev/null
```

Searches for files whose names contain `access` and `log`.

---

### Reading and Searching Text

```bash
grep "word" file.txt
```

Searches for a specific word or pattern inside a file.

Example:

```bash
grep "catsanddogs.jpg" access.log
```

Can be useful when searching web server logs.

---

## 2. Linux Fundamentals

### Users

Linux has different users with different permissions.

```bash
whoami
```

Shows the current user.

```bash
id
```

Shows the user's UID, GID and group memberships.

### Root

`root` is the administrator account in Linux.

Root has extensive permissions ove
