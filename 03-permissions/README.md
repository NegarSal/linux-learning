# Permissions 🔐

## 📚 Overview

Linux permissions control who can read, modify, or execute files and directories. They are one of the core security features of Linux.

---

## 🧠 Key Concepts

* **Owner** → File owner.
* **Group** → Users sharing the same permissions.
* **Others** → All other users.
* **Read (r)** → Read permission.
* **Write (w)** → Write permission.
* **Execute (x)** → Execute permission.

---

## 💻 Essential Commands

| Command  | Purpose                      |
| -------- | ---------------------------- |
| `ls -l`  | Show file permissions        |
| `ls -ld` | Show directory permissions   |
| `chmod`  | Change permissions           |
| `chown`  | Change file owner            |
| `chgrp`  | Change file group            |
| `umask`  | Show default permission mask |

---

## 🔍 Personal Notes

### 💡 Things I Learned

#### Default Permissions

* On my system, new files are created with **664** (`-rw-rw-r--`).
* On my system, new directories are created with **775** (`drwxrwxr-x`).
* Default permissions are controlled by **umask**.

---

#### Meaning of `r`, `w`, and `x`

| Permission | File             | Directory                                |
| ---------- | ---------------- | ---------------------------------------- |
| `r`        | Read the file    | List directory contents                  |
| `w`        | Modify the file  | Create/Delete files inside the directory |
| `x`        | Execute the file | Enter (traverse) the directory           |

---

#### Understanding `ls -l`

Example:

```text
-rw-rw-r-- 1 username groupname 1250 Jul 18 10:30 notes.txt
```

| Part           | Meaning                                          |
| -------------- | ------------------------------------------------ |
| `-`            | File type (`d` = Directory, `l` = Symbolic Link) |
| `rw-rw-r--`    | File permissions                                 |
| `1`            | Number of Hard Links                             |
| `username`     | Owner                                            |
| `groupname`    | Group                                            |
| `1250`         | File size (bytes)                                |
| `Jul 18 10:30` | Last modification time                           |
| `notes.txt`    | File name                                        |

> A **Hard Link** is another filename that points to the same data on disk. This number shows how many hard links point to the file.

---

#### `chmod`

* Changes file or directory permissions.

**Modes**

* **Symbolic Mode** → Uses letters (`u`, `g`, `o`, `a`) and operators (`+`, `-`, `=`).
* **Numeric Mode** → Uses numbers based on:

  * `r = 4`
  * `w = 2`
  * `x = 1`

---

#### Linux File Types

| Symbol | Type              |
| ------ | ----------------- |
| `-`    | Regular File      |
| `d`    | Directory         |
| `l`    | Symbolic Link     |
| `c`    | Character Device  |
| `b`    | Block Device      |
| `p`    | Named Pipe (FIFO) |
| `s`    | Socket            |

---

## ⚠️ Common Mistakes

* Confusing file permissions with directory permissions.
* Forgetting that `x` has different meanings for files and directories.
* Using `chmod 777` without understanding its security risks.

---

## 💡 Interview Tips

Be able to explain:

* Owner vs Group vs Others
* File vs Directory permissions
* How to read `ls -l`
* Symbolic Mode vs Numeric Mode in `chmod`
* Purpose of `umask`

---

## 📝 Summary

Linux permissions define access for **Owner**, **Group**, and **Others** using **Read**, **Write**, and **Execute** permissions. Understanding `ls -l`, `chmod`, and `umask` is essential for managing files securely.
