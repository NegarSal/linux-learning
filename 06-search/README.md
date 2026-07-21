# Search 🔎

## 📚 Overview

Linux provides powerful tools to search for files, directories, and commands. Knowing the right tool helps you locate files quickly and troubleshoot systems efficiently.

---

## 🧠 Key Concepts

- **find** → Search files and directories in real time.
- **locate** → Search using a pre-built database.
- **which** → Show the executable path of a command.
- **whereis** → Show executable, manual pages, and source files.
- **type** → Identify whether a command is a builtin, alias, function, or executable.

---

## 💻 Essential Commands

| Command | Purpose |
|---------|---------|
| `find` | Search files and directories |
| `locate` | Fast file search using a database |
| `updatedb` | Update the locate database |
| `which` | Show executable path |
| `whereis` | Show executable, manual, and source |
| `type` | Identify command type |

---

## 🔍 Personal Notes

### 💡 Things I Learned

- `find` searches the filesystem directly, while `locate` searches a database.

#### Useful `find` options

| Option | Purpose |
|--------|---------|
| `-name` | Search by filename |
| `-iname` | Case-insensitive filename search |
| `-type f` | Regular files only |
| `-type d` | Directories only |
| `-type l` | Symbolic links only |
| `-empty` | Empty files/directories |
| `-size` | Search by file size |
| `-user` | Search by owner |
---

### 🚧 Problems I Faced

#### `which` could not find `cd`

I expected:

```bash
which cd
```

to display a path.

Instead, it returned nothing.

I later learned that `cd` is a **Shell Builtin**, not an executable file, so `which` cannot locate it.

---

## ⚠️ Common Mistakes

- Forgetting that `locate` requires an updated database
- Mixing up `-name` and `-iname`

---

## 💡 Interview Tips

Be able to explain:

- `find` vs `locate`
- `which` vs `whereis`
- `-name` vs `-iname`
- `-type f` vs `-type d`
- Why `updatedb` is needed
- Shell Builtin vs Executable

---

## 📝 Summary

Linux provides several search utilities for different purposes. `find` performs real-time searches, `locate` provides fast database-based searches, and `which`, `whereis`, and `type` help identify command locations and types.
