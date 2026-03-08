# So Meta

### Description:

Find the flag in this `picture`.
Hint: What does meta mean in the context of files? / Ever heard of metadata?

### Commands / Steps:

```bash
# Step 1: This is actually straightforward. The challenge gives us an image file and the hint tells us about metadata. 

# Step 2: Download the file first.
wget [filelink]

# Step 3: Check the metadata of the file.
exiftool pico_img.png
# ExifTool Version Number         : 13.25
# File Name                       : pico_img.png
# Directory                       : .
# File Size                       : 109 kB
# File Modification Date/Time     : 2025:11:21 13:11:00-06:00
# File Access Date/Time           : 2026:03:08 11:35:16-05:00
# File Inode Change Date/Time     : 2026:03:08 11:35:16-05:00
# File Permissions                : -rw-rw-r--
# File Type                       : PNG
# File Type Extension             : png
# MIME Type                       : image/png
# Image Width                     : 600
# Image Height                    : 600
# Bit Depth                       : 8
# Color Type                      : RGB
# Compression                     : Deflate/Inflate
# Filter                          : Adaptive
# Interlace                       : Noninterlaced
# Software                        : Adobe ImageReady
# XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
# Creator Tool                    : Adobe Photoshop CS6 (Windows)
# Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
# Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
# Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
# Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
# Artist                          : picoCTF{s0_m3ta_19ebefe2}
# Image Size                      : 600x600
# Megapixels                      : 0.360
# ]
```

### Flag:

> picoCTF{s0_m3ta_19ebefe2}

### Notes / Tips

- **Metadata**: Hidden information stored in files (EXIF data, creation date, software used, GPS coordinates, etc.)
- **Tools**: `exiftool filename` (Linux/Mac) or `Get-ItemProperty filename | Format-List *` (PowerShell)
- **Common hiding spots**: Artist, Comment, Software, Copyright, or custom XMP fields
- **Alternative tools**: `strings filename`, `file filename`, or online EXIF viewers for quick analysis 


