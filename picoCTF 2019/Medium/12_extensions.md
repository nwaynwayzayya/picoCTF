# extensions

### Description:

This is a really weird text file. Can you find the flag?
Get the flag from `TXT`.
Hint: How do operating systems know what kind of file it is? (It's not just the ending!) / Make sure to submit the flag as picoCTF{XXXXX}

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filelink]

# Step 2: Read the contents of the file to see what in it first. 
cat flag.txt
# Many unreadable words are in the file. 

# Step 3: Check the file type.
file flag.txt
# flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

# Step 4: It's a png image file, with a wrong extension. Change the extension of the file.
cp flag.txt flag.png  # Alternative: mv flag.txt flag.png
# We'll get the flag after viewing the file.
```

### Flag:

> picoCTF{now_you_know_about_extensions}

### Notes / Tips

- `Extensions vs Content`: File extensions (.txt, .png, .jpg) are hints, but actual content determines file type
- `file` Command: Uses magic bytes database (/usr/share/misc/magic) to identify files


