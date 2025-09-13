# 🧠 Notes

## 🔢 Number Conversion & `bc`
- `bc` → Command-line calculator (can convert between bases).
- `ibase` → input base (default = 10)  
- `obase` → output base (default = 10)  
- **Order matters** → set `ibase` first if using a non-decimal input  

**Examples:**
```bash
# Decimal → Binary
echo "obase=2; 42" | bc
# Output: 101010

# Hex → Binary
echo "ibase=16; obase=2; 3D" | bc
# Output: 111101
```

## 🔤 Hex & ASCII Tricks
- `Prefix 0x` = number is in hexadecimal (base 16)

**Useful conversions:**

```bash
# Hex → Decimal
echo $((0x70))

# Decimal → ASCII
python3 -c "print(chr(112))"

# Hex → ASCII directly
python3 -c "print(chr(0x70))"
# 'chr()' in Python → converts a number into its corresponding ASCII/Unicode character.
```

## 🐍 Python Notes
- python [filename] → Run a Python script
- One-liner execution:
    - `python3 -c "your_code_here"`

**Example:** Convert stdin numbers to ASCII

```bash
nc mercury.picoctf.net 35652 | python3 -c "import sys;print(''.join(chr(int(i)) for i in sys.stdin.read().split()))"
```
**Explanation:**

- `sys.stdin.read()` → reads all input
- `.split()` → splits input into list items
- `int(i)` → converts each string to integer
- `chr(int(i))` → turns integer into ASCII character
- `''.join(...)` → joins characters into one string (like a flag)

## 🌐 Networking Basics
- `nc <host> <port>` → Connect via TCP/UDP and stream program output
- `ssh user@host -p <port>` → Securely connect to a remote machine
- `Pipe (|)` → Send output of first command into second as input
- `grep <pattern>` → Search for pattern in input/output
    - `-i` → Case-insensitive
    - `-R` or `-r` → Recursive search in all files
    - `-o "picoCTF{[^}]*}"` → Print only the flag text from noisy output

**Redirect output to a file:**

```bash
nc host port > output.txt
grep pico output.txt
```

## 📂 Linux Commands & Navigation
- `/` → Root directory
- `~` → Home directory
- `ls` → List files and directories
- `cd [directory]` → Change directory
- `cat [file]` → View file contents
- `&&` → Run next command only if the first one succeeds

**File search & flag hunting:**

```bash
grep -r "picoCTF{" .
find files -name "uber-secret.txt"
```
**Unzip files:**

```bash
unzip file.zip
```

## 🛠 Binary & File Inspection
- `file <filename>` → Show file type
- `strings <filename>` → Print human-readable strings inside a binary

**Combine with grep:**

```bash
strings static | grep pico
```

## ⚡ Productivity Tips
- Use tab completion to quickly navigate deep directory structures
- Redirect input from a file if a program asks for input:
    - `program < input.txt`

- For long/continuous outputs:
    - `grep --line-buffered` → show matches in real time
    - `timeout <seconds> command` → auto-stop after given time