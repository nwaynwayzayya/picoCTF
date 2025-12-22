# What Lies Within

### Description:

There's something in the `building`. Can you retrieve the flag?
Hint: There is data encoded somewhere... there might be an online decoder.

### Commands / Steps:

```bash
# Step 1: Download the png file.
wget {link to file}

# Step 2: The hint tells us that the flag is encoded in the png file. So let's check the metadata of the image first. 
exiftool buildings.png
# ExifTool Version Number         : 12.40
# File Name                       : buildings.png
# Directory                       : .
# File Size                       : 611 KiB
# File Modification Date/Time     : 2025:11:07 19:37:28+00:00
# File Access Date/Time           : 2025:12:22 18:37:14+00:00
# File Inode Change Date/Time     : 2025:12:22 18:36:59+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : PNG
# File Type Extension             : png
# MIME Type                       : image/png
# Image Width                     : 657
# Image Height                    : 438
# Bit Depth                       : 8
# Color Type                      : RGB with Alpha
# Compression                     : Deflate/Inflate
# Filter                          : Adaptive
# Interlace                       : Noninterlaced
# Image Size                      : 657x438
# Megapixels                      : 0.288

# Step 3: There's nothing much in the metadata. Let's try "zsteg" since the file is a png image.
zsteg buildings.png        # Alternative: There are many online tools on the internet for this as well.
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"
```

### Flag:

> picoCTF{h1d1ng_1n_th3_b1t5}

### Notes / Tips

- Steganography Type: LSB (Least Significant Bit) hiding in RGB channels
- Tool Used: zsteg - specialized for PNG/BMP stego detection
- False Positives: Ignore other outputs like "PGP Secret Sub-key" - just artifacts


