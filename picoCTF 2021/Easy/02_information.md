# information

### Objective:

Files can always be changed in a secret way. Can you find the flag? `cat.jpg`
Hint: Look at the details of the file

### Commands / Steps:

```bash
# Step 1: Download the cat.jpg.
wget https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg

# Step 2: We will look at the metadat of the file first, since the hint tells us to.
exiftool cat.jpg
# ExifTool Version Number         : 12.40
# File Name                       : cat.jpg
# Directory                       : .
# File Size                       : 858 KiB
# File Modification Date/Time     : 2021:03:15 18:24:46+00:00
# File Access Date/Time           : 2025:09:18 11:19:48+00:00
# File Inode Change Date/Time     : 2025:09:18 11:19:44+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : JPEG
# File Type Extension             : jpg
# MIME Type                       : image/jpeg
# JFIF Version                    : 1.02
# Resolution Unit                 : None
# X Resolution                    : 1
# Y Resolution                    : 1
# Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
# Copyright Notice                : PicoCTF
# Application Record Version      : 4
# XMP Toolkit                     : Image::ExifTool 10.80
# License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
# Rights                          : PicoCTF
# Image Width                     : 2560
# Image Height                    : 1598
# Encoding Process                : Baseline DCT, Huffman coding
# Bits Per Sample                 : 8
# Color Components                : 3
# Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
# Image Size                      : 2560x1598
# Megapixels                      : 4.1

# Step 3: The license number looks suspicious and it looks like base64 encoded. So we will try to decode it first to see if we can get the flag.
echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d
# The output is a flag.
```

### Flag:

> picoCTF{the_m3tadata_1s_modified}

### Notes / Tips

- `wget <link>` --> Network downloader.
- `exiftool <filename>` --> Lets you read and write meta data in files.
- `echo <string>` --> Displays a line of text.
- `base64 -d` --> Decode base64
- `Base64` is a way to encode binary/text data into ASCII characters — often used to hide info in metadata.


