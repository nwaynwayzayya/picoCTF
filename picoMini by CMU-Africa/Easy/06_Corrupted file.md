# Corrupted file

### Description:

This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?
Download the file `here`.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://challenge-files.picoctf.net/c_amiable_citadel/8646393bf40c0026e51065e57963b604edf0a9a73371e01d1af2865c050d3e68/file

# Step 2: Check file type.
file file
# Output- file: data

# Step 3: Let's check the headers to see what type of file this might be.
hexdump -C file | head -10  
# 00000000  5c 78 ff e0 00 10 4a 46  49 46 00 01 01 00 00 01  |\x....JFIF......|
# 00000010  00 01 00 00 ff db 00 43  00 08 06 06 07 06 05 08  |.......C........|
# 00000020  07 07 07 09 09 08 0a 0c  14 0d 0c 0b 0b 0c 19 12  |................|
# 00000030  13 0f 14 1d 1a 1f 1e 1d  1a 1c 1c 20 24 2e 27 20  |........... $.' |
# 00000040  22 2c 23 1c 1c 28 37 29  2c 30 31 34 34 34 1f 27  |",#..(7),01444.'|
# 00000050  39 3d 38 32 3c 2e 33 34  32 ff db 00 43 01 09 09  |9=82<.342...C...|
# 00000060  09 0c 0b 0c 18 0d 0d 18  32 21 1c 21 32 32 32 32  |........2!.!2222|
# 00000070  32 32 32 32 32 32 32 32  32 32 32 32 32 32 32 32  |2222222222222222|
# *
# 00000090  32 32 32 32 32 32 32 32  32 32 32 32 32 32 ff c0  |22222222222222..|

# Step 4: Normally, the jpeg files start with this "ff d8 ff e0". This file looks like a jpeg but the first two bytes are corrupted. So, let's fix the header. 
printf '\xff\xd8' | dd of=file bs=1 seek=0 conv=notrunc 2>/dev/null

# Step 5: Then we can display the file and get the flag inside.
display file
```

### Flag:

> picoCTF{r3st0r1ng_th3_by73s_939a65f5}

### Notes / Tips

- File Headers: Every file type has a unique "magic number" at the start
- JPEG Signature: Should be FF D8 FF E0
- Corruption: First 2 bytes were 5C 78 (ASCII for \x) instead of FF D8
- Tools: xxd/hexdump for header analysis, dd for binary editing
- File Command: When file returns "data", always check headers manually
- Binary Editing: Use dd with bs=1 and conv=notrunc for precise byte replacement


