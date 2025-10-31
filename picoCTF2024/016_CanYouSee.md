# CanYouSee

### Description:

How about some hide and seek?
Download this file `here`.

Hint: How can you view the information about the picture?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c_titan/4/unknown.zip

# Step 2: Unzip the file.
unzip unknown.zip
# Output: 
# Archive:  unknown.zip
#   inflating: ukn_reality.jpg

# Step 3: Let's check the information of the picture according to the hint.
exiftool ukn_reality.jpg
# Output: 
# ExifTool Version Number         : 12.40
# File Name                       : ukn_reality.jpg
# Directory                       : .
# File Size                       : 2.2 MiB
# File Modification Date/Time     : 2024:02:15 22:40:14+00:00
# File Access Date/Time           : 2024:02:15 22:40:14+00:00
# File Inode Change Date/Time     : 2025:10:31 17:32:29+00:00
# File Permissions                : -rw-r--r--
# File Type                       : JPEG
# File Type Extension             : jpg
# MIME Type                       : image/jpeg
# JFIF Version                    : 1.01
# Resolution Unit                 : inches
# X Resolution                    : 72
# Y Resolution                    : 72
# XMP Toolkit                     : Image::ExifTool 11.88
# Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==
# Image Width                     : 4308
# Image Height                    : 2875
# Encoding Process                : Baseline DCT, Huffman coding
# Bits Per Sample                 : 8
# Color Components                : 3
# Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
# Image Size                      : 4308x2875
# Megapixels                      : 12.4

# Step 4: The 'Attribution URL' looks suspicious. It looks like base64, so we will try decoding it. 
echo cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg== | base64 -d
# The decoded output is the flag.
```

### Flag:

> picoCTF{ME74D47A_HIDD3N_deca06fb}

### Notes / Tips

- `exiftool <filename>` → View metadata and EXIF data of image files
- `base64 -d` → Decode base64 encoded strings
- Check image metadata for hidden information in CTF challenges
- Look for suspicious fields like "Attribution URL", "Comment", or "Description" in EXIF data
- Base64 encoded strings often end with = or == padding


