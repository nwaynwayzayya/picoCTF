# Riddle Registry

### Description:

Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered.
Find the PDF file here `Hidden Confidential Document` and uncover the flag within the metadata.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://challenge-files.picoctf.net/c_amiable_citadel/5da2648ffaf783a1015aec626491641b7907e0991c16cb6c771aaaea387c18f6/confidential.pdf

# Step 2: The question tells us to find the flag within the metadata so let's get the metadata first. 
exiftool confidential.pdf
# ExifTool Version Number         : 12.40
# File Name                       : confidential.pdf
# Directory                       : .
# File Size                       : 178 KiB
# File Modification Date/Time     : 2025:11:07 19:17:36+00:00
# File Access Date/Time           : 2025:11:20 16:30:10+00:00
# File Inode Change Date/Time     : 2025:11:20 16:30:10+00:00
# File Permissions                : -rw-rw-r--
# File Type                       : PDF
# File Type Extension             : pdf
# MIME Type                       : application/pdf
# PDF Version                     : 1.7
# Linearized                      : No
# Page Count                      : 1
# Producer                        : PyPDF2
# Author                          : cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV8zNTc4NzM5YX0=

# Step 3: The metadata field for 'Author' looks like base64 encoded. Let's try decoding it first to see if we can get the flag.
echo cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV8zNTc4NzM5YX0= | base64 -d
```

### Flag:

> picoCTF{puzzl3d_m3tadata_f0und!_3578739a}

### Notes / Tips

- Tool Used: exiftool - extracts metadata from files
- Location: Flag was hidden in PDF's "Author" metadata field
- Encoding: Base64 - common way to hide text in metadata
- Pattern: Always check all metadata fields, not just obvious ones


