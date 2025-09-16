# Glory of the Garden

### Objective:

This `garden` contains more than it seems.
Hint: What is a hex editor?

### Commands / Steps:

```bash
# Step 1: We download the file.
wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg

# Step 2: Use exiftool to check for any clues in the metadata first.
exiftool garden.jpg
# ExifTool Version Number         : 12.40
# File Name                       : garden.jpg
# Directory                       : .
# File Size                       : 2.2 MiB
# File Modification Date/Time     : 2020:10:26 18:39:31+00:00
# File Access Date/Time           : 2025:09:16 08:57:46+00:00
# File Inode Change Date/Time     : 2025:09:16 08:57:39+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : JPEG
# File Type Extension             : jpg
# MIME Type                       : image/jpeg
# JFIF Version                    : 1.01
# Resolution Unit                 : inches
# X Resolution                    : 72
# Y Resolution                    : 72
# Profile CMM Type                : Linotronic
# Profile Version                 : 2.1.0
# Profile Class                   : Display Device Profile
# Color Space Data                : RGB
# Profile Connection Space        : XYZ
# Profile Date Time               : 1998:02:09 06:49:00
# Profile File Signature          : acsp
# Primary Platform                : Microsoft Corporation
# CMM Flags                       : Not Embedded, Independent
# Device Manufacturer             : Hewlett-Packard
# Device Model                    : sRGB
# Device Attributes               : Reflective, Glossy, Positive, Color
# Rendering Intent                : Perceptual
# Connection Space Illuminant     : 0.9642 1 0.82491
# Profile Creator                 : Hewlett-Packard
# Profile ID                      : 0
# Profile Copyright               : Copyright (c) 1998 Hewlett-Packard Company
# Profile Description             : sRGB IEC61966-2.1
# Media White Point               : 0.95045 1 1.08905
# Media Black Point               : 0 0 0
# Red Matrix Column               : 0.43607 0.22249 0.01392
# Green Matrix Column             : 0.38515 0.71687 0.09708
# Blue Matrix Column              : 0.14307 0.06061 0.7141
# Device Mfg Desc                 : IEC http://www.iec.ch
# Device Model Desc               : IEC 61966-2.1 Default RGB colour space - sRGB
# Viewing Cond Desc               : Reference Viewing Condition in IEC61966-2.1
# Viewing Cond Illuminant         : 19.6445 20.3718 16.8089
# Viewing Cond Surround           : 3.92889 4.07439 3.36179
# Viewing Cond Illuminant Type    : D50
# Luminance                       : 76.03647 80 87.12462
# Measurement Observer            : CIE 1931
# Measurement Backing             : 0 0 0
# Measurement Geometry            : Unknown
# Measurement Flare               : 0.999%
# Measurement Illuminant          : D65
# Technology                      : Cathode Ray Tube Display
# Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
# Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
# Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
# Image Width                     : 2999
# Image Height                    : 2249
# Encoding Process                : Baseline DCT, Huffman coding
# Bits Per Sample                 : 8
# Color Components                : 3
# Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
# Image Size                      : 2999x2249
# Megapixels                      : 6.7
####################################
# Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
# Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
# Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
# This tells us it has binary data in it.

# Step 3: Use xxd tool to view the binary representation of the file.
xxd -b garden.jpg
# Output: A lot of hex value outputs.
xxd -b garden.jpg | head
# 00000000: 11111111 11011000 11111111 11100000 00000000 00010000  ......
# 00000006: 01001010 01000110 01001001 01000110 00000000 00000001  JFIF..
# 0000000c: 00000001 00000001 00000000 01001000 00000000 01001000  ...H.H
# 00000012: 00000000 00000000 11111111 11100010 00001100 01011000  .....X
# 00000018: 01001001 01000011 01000011 01011111 01010000 01010010  ICC_PR
# 0000001e: 01001111 01000110 01001001 01001100 01000101 00000000  OFILE.
# 00000024: 00000001 00000001 00000000 00000000 00001100 01001000  .....H
# 0000002a: 01001100 01101001 01101110 01101111 00000010 00010000  Lino..
# 00000030: 00000000 00000000 01101101 01101110 01110100 01110010  ..mntr
# 00000036: 01010010 01000111 01000010 00100000 01011000 01011001  RGB XY
xxd -b garden.jpg | tail
# 0023055c: 11111111 11011001 01001000 01100101 01110010 01100101  ..Here
# 00230562: 00100000 01101001 01110011 00100000 01100001 00100000   is a 
# 00230568: 01100110 01101100 01100001 01100111 00100000 00100010  flag "
# 0023056e: 01110000 01101001 01100011 01101111 01000011 01010100  picoCT
# 00230574: 01000110 01111011 01101101 01101111 01110010 01100101  F{more
# 0023057a: 01011111 01110100 01101000 01100001 01101110 01011111  _than_
# 00230580: 01101101 00110011 00110011 01110100 01110011 01011111  m33ts_
# 00230586: 01110100 01101000 01100101 01011111 00110011 01111001  the_3y
# 0023058c: 00110011 00110110 00110101 00110111 01000010 01100001  3657Ba
# 00230592: 01000010 00110010 01000011 01111101 00100010 00001010  B2C}".
```

### Flag:

> picoCTF{more_than_m33ts_the_3y3657BaB2C}

### Notes / Tips

- Use tools like xxd, hexdump, or a GUI hex editor to inspect file contents.

- We can also quickly find flags using:

    - `strings garden.jpg | grep picoCTF`

    - This automatically prints out human-readable strings — often a quick win.


