# Filesystem 📂

## 📚 Overview

The Linux filesystem is organized as a single hierarchical tree that starts from the root directory (`/`). Every file, directory, storage device, and mounted filesystem exists somewhere within this tree.

Understanding the filesystem layout is one of the most important foundations of Linux administration.

---

## 🧠 Key Concepts

### Root Directory

The root directory (`/`) is the top level of the Linux filesystem hierarchy.

### Home Directory

The home directory (`~`) stores personal files and configuration for each user.

Example:

```text
/home/username
```

### Current Directory

`.` refers to the current working directory.

### Parent Directory

`..` refers to the parent directory.

### Absolute Path

An absolute path always starts from the root directory (`/`).

Example:

```text
/home/user/Documents
```

### Relative Path

A relative path starts from the current directory.

Example:

```text
Documents
```

---

## 📂 Important Directories

| Directory | Purpose                         |
| --------- | ------------------------------- |
| `/`       | Root of the filesystem          |
| `/home`   | User home directories           |
| `/etc`    | System configuration files      |
| `/usr`    | User applications and utilities |
| `/bin`    | Essential system commands       |
| `/var`    | Variable data such as logs      |
| `/tmp`    | Temporary files                 |

---

## 💻 Essential Commands

| Command | Purpose                             |
| ------- | ----------------------------------- |
| `pwd`   | Print the current working directory |
| `cd`    | Change the current directory        |
| `ls`    | List directory contents             |
| `tree`  | Display the directory structure     |
| `mkdir` | Create directories                  |
| `touch` | Create empty files                  |
| `cp`    | Copy files and directories          |
| `mv`    | Move or rename files/directories    |
| `rm`    | Remove files                        |
| `rmdir` | Remove empty directories            |
| `file`  | Identify the file type              |
| `stat`  | Display detailed file information   |

---

## 🔍 Personal Notes

These are personal discoveries and notes collected while practicing Linux. They help me remember concepts, common mistakes, and useful tricks.

### 💡 Things I Learned

#### Understanding the filesystem

A storage device (such as an HDD or SSD) is like a large library, and files are like the books inside it.

A **filesystem** is like the librarian. It organizes the books, keeps them in the right places, and knows exactly where each one is located so it can be found quickly.

Without a filesystem, all data would exist on the disk without any organization.

---

#### Why do some commands require `-r`?

The `-r` option stands for **recursive**.

A directory may contain files and even other directories. When using commands like `cp` or `rm`, Linux needs permission to enter the directory and process everything inside it.

Example:

```bash
cp -r project backup
```

Copies the entire directory, including all files and subdirectories.

```bash
rm -r project
```

Removes the directory and everything inside it.

---

#### Why are `rm` and `rm -r` different?

`rm` removes files only.

```bash
rm notes.txt
```

`rm -r` removes directories recursively.

```bash
rm -r project
```

Linux does not remove directories with a simple `rm` by default because this helps prevent accidental deletion of large amounts of data.

**Rule to remember:**

> If a command needs to work on a directory and everything inside it, it usually requires the `-r` (recursive) option.

---

### 🚧 Problems I Faced

#### Removing non-empty directories

`rmdir` only removes **empty** directories.

To remove a directory together with all of its contents:

```bash
rm -r directory_name
```

---

#### Displaying the project tree

To display the project structure while hiding the `.git` directory:

```bash
tree -a -I ".git"
```

Useful when documenting GitHub repositories.

---

#### Viewing directory information

To display information about the directory itself (instead of its contents):

```bash
ls -ld directory_name
```

Example:

```bash
ls -ld linux-learning
```

Useful for checking directory permissions, ownership, and metadata.

---

## ⚠️ Common Mistakes

* Confusing `/` with `~`
* Confusing `.` with `..`
* Using a relative path when an absolute path is required
* Assuming Linux uses drive letters like Windows
* Forgetting to use `-r` when copying or removing directories

---

## 💡 Interview Tips

Be able to explain:

* What is a filesystem?
* Absolute Path vs Relative Path
* `/` vs `~`
* `.` vs `..`
* Why Linux uses a single filesystem tree
* Purpose of `/etc`, `/home`, `/usr`, `/var`, and `/tmp`
* Difference between `rm` and `rm -r`
* Meaning of the recursive (`-r`) option

---

## 📝 Summary

The Linux filesystem is a single hierarchical tree that starts at the root directory (`/`).

Understanding directories, paths, navigation commands, and basic filesystem operations is essential before learning more advanced Linux topics such as permissions, links, storage management, and mounting filesystems.
