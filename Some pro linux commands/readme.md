# Some Pro Linux Commands

This document offers concise, practical notes on powerful text-processing utilities commonly used by advanced users. Each section includes basic description and sample commands to get started.

## `awk`
A versatile text-processing language, often used for pattern scanning and processing. Works particularly well with columnar data.

**Examples:**
```bash
# print second column of a file
awk '{print $2}' file.txt

# sum values in third column
awk '{sum += $3} END {print sum}' data.csv

# filter lines where first field equals "error"
awk '$1 == "error"' logfile
```

## `sed`
Stream editor for filtering and transforming text. Ideal for substitution, deletion, and simple text manipulations.

**Examples:**
```bash
# replace "foo" with "bar" in-place
sed -i 's/foo/bar/g' file.txt

# delete lines 2 through 4
sed '2,4d' file.txt

# print only lines matching pattern
sed -n '/pattern/p' file.txt
```

## `grep`
Searches input for lines matching a regular expression. Supports recursive search, color highlighting, and extended regex.

**Examples:**
```bash
# find "TODO" in source files
grep -R --color=auto "TODO" src/

# show line numbers with matches
grep -n "main" program.c

# use extended regex
grep -E "error|warning" logfile
```

---

Keep this cheat sheet for quick reference when working with text processing tools in Linux! 