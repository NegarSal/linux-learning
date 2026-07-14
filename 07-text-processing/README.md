# Text Processing

## Overview

Text processing is one of the most important skills in Linux. Most Linux tools follow the Unix philosophy:

> Do one thing and do it well.

Instead of using one large program, Linux combines many small tools together using pipelines (`|`).

This section contains the basic text-processing commands learned during Linux Essentials.

---

# Commands

## cat

### Purpose

Display the contents of one or more files.

### Syntax

```bash
cat file.txt
```

### Examples

```bash
cat /etc/passwd
```

---

## less

### Purpose

View large files page by page.

### Syntax

```bash
less file.txt
```

Useful keys:

* Space → Next page
* b → Previous page
* /text → Search
* q → Quit

---

## head

### Purpose

Display the beginning of a file.

### Syntax

```bash
head file.txt
head -5 file.txt
```

---

## tail

### Purpose

Display the end of a file.

### Syntax

```bash
tail file.txt
tail -5 file.txt
tail -f logfile
```

---

## grep

### Purpose

Search for text inside files.

### Syntax

```bash
grep "text" file
```

### Useful options

* `-i` Ignore case
* `-n` Show line numbers
* `-v` Invert match
* `-c` Count matches

---

## cut

### Purpose

Extract specific fields from each line.

### Syntax

```bash
cut -d ":" -f1 /etc/passwd
```

### Useful options

* `-d` Delimiter
* `-f` Field number

---

## sort

### Purpose

Sort lines alphabetically or numerically.

### Useful options

* `-r` Reverse order
* `-n` Numeric sort
* `-u` Remove duplicate lines after sorting

---

## uniq

### Purpose

Remove adjacent duplicate lines.

### Useful options

* `-c` Count duplicate lines
* `-d` Show only duplicated lines

> Note: `uniq` only removes consecutive duplicate lines. It is usually used together with `sort`.

---

## wc

### Purpose

Count lines, words, or bytes.

### Useful options

* `-l` Lines
* `-w` Words
* `-c` Bytes

---

## tee

### Purpose

Display output on the screen and save it to a file at the same time.

### Syntax

```bash
command | tee output.txt
```

---

# Pipelines

One of Linux's greatest strengths is combining commands together.

Example:

```bash
cut -d ":" -f7 /etc/passwd | sort | uniq
```

Example:

```bash
grep "/bin/bash" /etc/passwd | wc -l
```

---

# Common Mistakes

* Using `uniq` without `sort`.
* Forgetting the delimiter when using `cut`.
* Using `sort` instead of `sort -n` for numbers.
* Confusing `wc -l` (lines) with `wc -w` (words).
* Forgetting that `tee` both displays and saves output.

---

# Summary

Commands covered in this section:

* cat
* less
* head
* tail
* grep
* cut
* sort
* uniq
* wc
* tee

These commands form the foundation of text processing in Linux and will be used throughout LPIC-1, Bash scripting, and DevOps.
