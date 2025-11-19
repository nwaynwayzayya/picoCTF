# RED

### Description:

RED, RED, RED, RED
Download the image: `red.png`

### Commands / Steps:

```bash
# Step 1: Download the image. 
wget <imagelink>

# Step 2: The image just look like a red square so let's check the metadata of the image.
exiftool red.png
# ExifTool Version Number         : 12.40
# File Name                       : red.png
# Directory                       : .
# File Size                       : 796 bytes
# File Modification Date/Time     : 2025:03:06 03:34:15+00:00
# File Access Date/Time           : 2025:11:19 19:16:20+00:00
# File Inode Change Date/Time     : 2025:11:19 19:16:16+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : PNG
# File Type Extension             : png
# MIME Type                       : image/png
# Image Width                     : 128
# Image Height                    : 128
# Bit Depth                       : 8
# Color Type                      : RGB with Alpha
# Compression                     : Deflate/Inflate
# Filter                          : Adaptive
# Interlace                       : Noninterlaced
# Poem                            : Crimson heart, vibrant and bold,.Hearts flutter at your sight..Evenings glow softly red,.Cherries burst with sweet life..Kisses linger with your warmth..Love deep as merlot..Scarlet leaves falling softly,.Bold in every stroke.
# Image Size                      : 128x128
# Megapixels                      : 0.016

# Step 3: We don't get anything like a flag from the exiftool, so let's use another tool called, 'steghide' to check for hidden data. 
steghide red.png
# meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."
# b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="
# b1,rgba,msb,xy      .. file: OpenPGP Public Key
# b2,g,lsb,xy         .. text: "ET@UETPETUUT@TUUTD@PDUDDDPE"
# b2,rgb,lsb,xy       .. file: OpenPGP Secret Key
# b2,bgr,msb,xy       .. file: OpenPGP Public Key
# b2,rgba,lsb,xy      .. file: OpenPGP Secret Key
# b2,rgba,msb,xy      .. text: "CIkiiiII"
# b2,abgr,lsb,xy      .. file: OpenPGP Secret Key
# b2,abgr,msb,xy      .. text: "iiiaakikk"
# b3,rgba,msb,xy      .. text: "#wb#wp#7p"
# b3,abgr,msb,xy      .. text: "7r'wb#7p"
# b4,b,lsb,xy         .. file: 0421 Alliant compact executable not stripped

# Step 4: The 'b1,rgba,lsb,xy      .. text: ' looks like base64 encoded string so, let's decode it to see if it's a flag. 
echo cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ== | base64 -d
# We get the hidden flag from this. 
```

### Flag:

> picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

### Notes / Tips

- Tools Used:

    - exiftool - Check image metadata
    - steghide - Detect steganography in images
    - base64 -d - Decode base64 strings


