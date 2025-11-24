# DISKO 1

### Description:

Can you find the flag in this disk image?
Download the disk image `here`.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c/537/disko-1.dd.gz

# Step 2: It's a gunzip file so let's decompress it.
gunzip disko-1.dd.gz

# Step 3: Then we will extract only the strings from the file and find "pico" to see if we can find the flag that way.
strings disko-1.dd | grep pico
# We got the flag.
```

### Flag:

> picoCTF{1t5_ju5t_4_5tr1n9_be6031da}

### Notes / Tips

- `.dd files`: Disk image/forensic files containing raw disk data
- `gunzip`: Decompresses .gz files
- `strings`: Extracts readable text from binary files
- `grep pico`: Searches for the flag pattern in extracted text


