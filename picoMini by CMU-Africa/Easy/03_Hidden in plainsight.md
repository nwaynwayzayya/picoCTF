# Hidden in plainsight

### Description:

Description
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.
Download the jpg image `here`.

### Commands / Steps:

```bash
# Step 1: Download the image.
wget https://challenge-files.picoctf.net/c_amiable_citadel/58f49cf585a3e6073ccd6a3ae03903dfd71567a2db9101645b428ac6820fb3cf/img.jpg

# Step 2: Check the metadata of the image.
exiftool img.jpg
# Output:
# ExifTool Version Number         : 12.40
# File Name                       : img.jpg
# Directory                       : .
# File Size                       : 72 KiB
# File Modification Date/Time     : 2025:11:07 19:17:34+00:00
# File Access Date/Time           : 2025:11:21 18:24:49+00:00
# File Inode Change Date/Time     : 2025:11:21 18:24:49+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : JPEG
# File Type Extension             : jpg
# MIME Type                       : image/jpeg
# JFIF Version                    : 1.01
# Resolution Unit                 : None
# X Resolution                    : 1
# Y Resolution                    : 1
# Comment                         : c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9
# Image Width                     : 640
# Image Height                    : 640
# Encoding Process                : Baseline DCT, Huffman coding
# Bits Per Sample                 : 8
# Color Components                : 3
# Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
# Image Size                      : 640x640
# Megapixels                      : 0.410

# Step 3: Check the metadata for clues.
# Comment: c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9  --> Base64
# Decoded: steghide:cEF6endvcmQ=
# Password: cEF6endvcmQ=   Decoded: pAzzword

# Step 4: Use 'steghide' to extract the hidden data.
steghide extract -sf img.jpg
# Enter the password from the previous step when prompted.

# Step 5: Then the flag will be extracted from the image and then saved into a file.
```

### Flag:

> picoCTF{h1dd3n_1n_1m4g3_871ba555}

### Notes / Tips

- Tools Used: exiftool, base64, steghide
- Method: Steganography with password-protected hidden data
- Clue Chain: Base64 in metadata → steghide password → extract hidden file
- Common CTF Pattern: Metadata often contains clues for steganography challenges


