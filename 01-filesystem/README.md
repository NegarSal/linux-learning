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

```bash
pwd
```

Print the current working directory.

```bash
cd
```

Change directory.

```bash
ls
```

List directory contents.

```bash
tree
```

Display the directory structure as a tree.

---

## ⚠️ Common Mistakes

* Confusing `/` with `~`
* Confusing `.` with `..`
* Using relative paths when an absolute path is required
* Assuming Linux uses drive letters like Windows

---

## 💡 Interview Tips

Be able to explain:

* Absolute Path vs Relative Path
* `/` vs `~`
* `.` vs `..`
* Why Linux uses a single filesystem tree
* Purpose of `/etc`, `/home`, and `/var`

---

## 📝 Summary

In Linux, everything is organized under a single filesystem tree that begins at the root directory (`/`).

Understanding directories, paths, and basic navigation commands is essential before learning more advanced Linux topics.
