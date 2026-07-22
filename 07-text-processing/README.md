# Text Processing 📝

## 📚 Overview

Text processing is one of the most important skills in Linux. Most Linux tools follow the Unix philosophy:

> **Do one thing and do it well.**

Instead of using one large program, Linux combines many small tools together using pipelines (`|`).

---

## 🧠 Key Concepts

- **Text Processing** → Reading, filtering, sorting, and manipulating text.
- **Pipeline (`|`)** → Pass the output of one command to another.
- **Standard Input (stdin)** → Input received from another command or keyboard.
- **Standard Output (stdout)** → Default command output.

---

## 💻 Essential Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `cat` | Display file contents | `cat file.txt` |
| `less` | View large files page by page | `less file.txt` |
| `head` | Show the beginning of a file | `head -5 file.txt` |
| `tail` | Show the end of a file | `tail -5 file.txt` / `tail -f logfile` |
| `grep` | Search text inside files | `grep "text" file` |
| `cut` | Extract specific fields | `cut -d ":" -f1 /etc/passwd` |
| `sort` | Sort lines | `sort file.txt` |
| `uniq` | Remove adjacent duplicate lines | `sort file.txt \| uniq` |
| `wc` | Count lines, words, or bytes | `wc -l file.txt` |
| `tee` | Display and save output simultaneously | `command \| tee output.txt` |

---

## 🔍 Personal Notes

### 💡 Things I Learned

- `tail -f` is useful for monitoring log files in real time.
- `uniq` only removes **adjacent** duplicate lines, so it is usually used after `sort`.

### Useful `grep` options

| Option | Purpose |
|--------|---------|
| `-i` | Ignore case |
| `-n` | Show line numbers |
| `-v` | Invert match |
| `-c` | Count matching lines |

### Useful `cut` options

| Option | Purpose |
|--------|---------|
| `-d` | Specify delimiter |
| `-f` | Select field |

### Useful `sort` options

| Option | Purpose |
|--------|---------|
| `-r` | Reverse order |
| `-n` | Numeric sort |
| `-u` | Remove duplicate lines after sorting |

### Useful `uniq` options

| Option | Purpose |
|--------|---------|
| `-c` | Count duplicate lines |
| `-d` | Show only duplicated lines |

### Useful `wc` options

| Option | Purpose |
|--------|---------|
| `-l` | Count lines |
| `-w` | Count words |
| `-c` | Count bytes |

---

### 🚧 Problems I Faced

#### `uniq` did not remove all duplicate lines

I learned that `uniq` only removes **consecutive** duplicate lines.

The correct approach is:

```bash
sort file.txt | uniq
```

---

## ⚠️ Common Mistakes

- Using `uniq` without `sort`
- Forgetting the delimiter when using `cut`
- Using `sort` instead of `sort -n` for numbers
- Confusing `wc -l` (lines) with `wc -w` (words)
- Forgetting that `tee` both displays and saves output

---

## 💡 Interview Tips

Be able to explain:

- `cat` vs `less`
- `head` vs `tail`
- `grep`
- `cut`
- `sort`
- `uniq`
- `wc`
- `tee`
- Why `uniq` is usually used with `sort`
- How pipelines (`|`) work

---

## 📝 Summary

Linux text-processing tools are designed to work together. Commands like `grep`, `cut`, `sort`, `uniq`, `wc`, and `tee` are essential for filtering, analyzing, and processing text, especially when combined with pipelines.

