# Links 🔗

## 📚 Overview

Links allow multiple names or paths to reference files and directories. Linux supports two types of links: **Hard Links** and **Symbolic (Soft) Links**.

---

## 🧠 Key Concepts

* **Hard Link** → Another name for the same inode.
* **Symbolic Link (Soft Link)** → A file that stores the path to another file or directory.
* **inode** → The real identity of a file in Linux.
* **Broken Link** → A symbolic link whose target no longer exists.

---

## 💻 Essential Commands

| Command  | Purpose                        |
| -------- | ------------------------------ |
| `ln`     | Create a Hard Link             |
| `ln -s`  | Create a Symbolic Link         |
| `ls -li` | Display inode numbers          |
| `stat`   | Show detailed file information |

---

## 🔍 Personal Notes

### 💡 Things I Learned

* Linux identifies files by **inode**, not by filename.
* Hard Links share the **same inode**.
* Symbolic Links have **their own inode**.
* Copying a file creates a **new inode**.
* A Symbolic Link is similar to a **shortcut**.
* `ls -li` displays inode numbers.
* `ls -l` shows the **Hard Link count**.

---

### 🚧 Problems I Faced

#### Difference between Copy and Hard Link

| Copy                | Hard Link                   |
| ------------------- | --------------------------- |
| Creates a new inode | Shares the same inode       |
| Independent file    | Same file with another name |

---

#### Why are Symbolic Link permissions always `lrwxrwxrwx`?

The permissions shown for a Symbolic Link are **not actually used**.

Linux checks the permissions of the **target file**, not the link itself.

---

## ⚠️ Common Mistakes

* Confusing Hard Links with copied files.
* Assuming Symbolic Links continue to work after deleting the target file.
* Confusing inode with filename.

---

## 💡 Interview Tips

Be able to explain:

* Hard Link vs Symbolic Link
* inode
* Copy vs Hard Link
* Broken Symbolic Link

---

## 📝 Summary

Hard Links and Symbolic Links solve different problems. Hard Links create another name for the same inode, while Symbolic Links store a path to another file or directory. Understanding **inode** is the key to understanding how Linux links work.
