# Wave A Flag

### Objective:

Can you invoke help flags for a tool or binary? `This program` has extraordinarily helpful information...

### Commands / Steps:

```bash
# Step 1: First, we download the file with the link of `This program`.
wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm

# Step 2: Checked the file type.
file warm
# Output
# warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=01b148cdedfc38125cac0d87e0537466d47927b1, with debug_info, not stripped

# Step 3: Try executing the file.
./warm
# Output
# -bash: ./warm: Permission denied

# Step 4: Make the file executable
chmod +x warm

# Step 5: Execute the file again. 
./warm
# Output
# Hello user! Pass me a -h to learn what I can do!

# Step 6: Followed the intruction.
./warm -h
# Output
# Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
```

### Flag:

> picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}

### Notes / Tips

- `./[filename]` --> Run or execute the file
- `chmod +x` --> Give file the permission to be executed
- `[command] -h` or `[command] -help` --> Get more information about the commands


