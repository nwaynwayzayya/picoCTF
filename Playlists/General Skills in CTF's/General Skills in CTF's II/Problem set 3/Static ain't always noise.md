# Static ain't always noise

### Objective:

Can you look at the data in this binary: `static`? This `BASH script` might help!


### Commands / Steps:

```bash
# Step 1: Download the files.
wget https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static && wget https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/ltdis.sh

# Step 2: Check the file type.
file static
# Output: ELF 64-bit LSB executable (not stripped).
# This means it's a compiled binary.

# Step 3: Look for human readable strings inside the binary.
strings static | grep pico
```

### Flag:

> picoCTF{d15a5m_t34s3r_6f8c8200}

### Notes / Tips

- `wget <url>` --> Download a file from the web.
- `file <filename> ` --> Shows the file type (text, binary, ELF executable, etc).
- `cat <filename>` --> View the contents of a file.
- `grep <string> <filename>` --> Find the <string> in a file.
- The provided `ltdis.sh` script was a hint for disassembling the binary, but for this challenge it wasn’t needed — `strings` alone reveals the flag.


