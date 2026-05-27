# Linux Fundamentals – Read and Write Text Files

## File Creation

### Command
```bash
touch notes.txt
```

Created an empty file named `notes.txt`.

---

## Writing to File

### Command
```bash
echo "Line 1" > notes.txt
```

Added first line to the file using overwrite redirection.

### Command
```bash
echo "Line 2" >> notes.txt
```

Appended second line to the file.

### Command
```bash
echo "Line 3" | tee -a notes.txt
```

Displayed and appended text to the file using `tee`.

---

## Reading File Content

### Command
```bash
cat notes.txt
```

Displayed complete file content.

### Command
```bash
head -n 2 notes.txt
```

Displayed first 2 lines from the file.

### Command
```bash
tail -n 2 notes.txt
```

Displayed last 2 lines from the file.

---

## Observations

- `>` overwrites file content
- `>>` appends content
- `tee -a` appends and displays output
- `cat`, `head`, and `tail` help inspect files quickly