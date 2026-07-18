# Users & Groups 👥

## 📚 Overview

Linux is a multi-user operating system where every user has a unique identity. Users and groups help manage access to files, directories, and system resources securely.

---

## 🧠 Key Concepts

* **User** → An identity in Linux.
* **Group** → A collection of users.
* **Root** → The system administrator with full privileges.
* **UID** → Unique numeric identifier for a user.
* **GID** → Unique numeric identifier for a group.
* **Regular User** → Human user.
* **System User** → Created for services and applications. They usually do not log into the system.

---

## 📂 Important Files

| File           | Purpose                     |
| -------------- | --------------------------- |
| `/etc/passwd`  | User account information    |
| `/etc/group`   | Group information           |
| `/etc/sudoers` | Users allowed to run `sudo` |

---

## 💻 Essential Commands

| Command       | Purpose                        |
| ------------- | ------------------------------ |
| `whoami`      | Show current username          |
| `id`          | Show UID, GID, and groups      |
| `groups`      | List group memberships         |
| `echo $USER`  | Display current username       |
| `echo $HOME`  | Display home directory         |
| `echo $SHELL` | Display current login shell    |
| `su`          | Switch to another user         |
| `sudo`        | Run a command as administrator |

---

## 🔍 Personal Notes

### 💡 Things I Learned

* Linux identifies users by **UID**, not by username.
* Groups simplify permission management.
* System users are created for services, not humans.
* `sudo` executes **one command** as Root, while `su` switches completely to another user.
* Linux follows the **Principle of Least Privilege**.

### 🚧 Problems I Faced

#### `/etc/passwd` does not store passwords

I learned that passwords are **not** stored in `/etc/passwd`.

The second field contains only:

```text
x
```

Actual password hashes are stored elsewhere.

---

#### Understanding the fields in `/etc/passwd`

Example:

```text
user:x:1000:1000:user:/home/user:/bin/zsh
```

| Field        | Description              |
| ------------ | ------------------------ |
| `user`       | Username                 |
| `x`          | Password placeholder     |
| `1000`       | UID                      |
| `1000`       | Primary GID              |
| `user`       | User description (GECOS) |
| `/home/user` | Home directory           |
| `/bin/zsh`   | Login shell              |

---

#### Extracting the Home Directory

```bash
grep "$(whoami)" /etc/passwd | cut -d: -f6
```

---

## ⚠️ Common Mistakes

* Confusing Username with UID
* Confusing User with Group
* Confusing `/etc/passwd` with `/etc/group`
* Assuming every user is a human user
* Using Root unnecessarily
* Confusing `sudo` with `su`

---

## 💡 Interview Tips

Be able to explain:

* User vs Group
* Root vs Regular User
* Regular User vs System User
* UID vs GID
* Why Linux uses UID instead of usernames
* Purpose of `/etc/passwd`
* Purpose of `/etc/group`
* Difference between `sudo` and `su`
* Why working as Root is discouraged

---

## 📝 Summary

Linux is a multi-user operating system where every user has a unique identity (UID), belongs to one or more groups, and has a home directory and login shell.

Groups simplify permission management, while `sudo` allows users to perform administrative tasks safely without logging in as Root.
