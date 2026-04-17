# Pitter, Patter, Platters

### Description:
'Suspicious' is written all over this disk image.
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
Download `suspicious.dd.sda1`

Hint: It may help to analyze this image in multiple ways: as a blob, and as an actual mounted disk. / Have you heard of slack space? There is a certain set of tools that now come with Ubuntu that I'd recommend for examining that disk space phenomenon...

### Commands / Steps:

```bash
# Step 1: Download the file. 
wget <filelink>

# Step 2: It's a raw disk image file, so the first thing we can do is check what files are in there.
fls -r suspicious.dd.sda1
# From the output, we can see a lot of different files including one interesting file:
# r/r 12: suspicious-file.txt

# Step 3: Let's extract that file from the disk and then view the contents of the file.
icat suspicious.dd.sda1 12 > suspicious-file.txt
cat suspicious-file.txt
# Nothing to see here! But you may want to look here -->

# Step 4: This was where it got tricky for me. But after a few research, I found the right way. 
# We will use the command 'istat' from The Sleuth Kit, which can show us the metadata of that suspicious-file.txt and lists the specific physical sectors/blocks assigned to that file.
istat suspicious.dd.sda1 12
# inode: 12
# Allocated
# Group: 0
# Generation Id: 3646402035
# uid / gid: 0 / 0
# mode: rrw-r--r--
# size: 55
# num of links: 1

# Inode Times:
# Accessed:       2020-09-30 08:15:59 (CDT)
# File Modified:  2020-09-30 00:17:23 (CDT)
# Inode Modified: 2020-09-30 08:15:54 (CDT)

# Direct Blocks:
# 2049

# Step 5: After this, we'll use 'blkcat' to read block 2049.
blkcat suspicious.dd.sda1 2049
# Output:
# Nothing to see here! But you may want to look here -->
# }3986312f_3<_|Lm_111t5_3b{FTCocip

# Step 6: From there, we can just reverse the string to get the flag.
echo '}3986312f_3<_|Lm_111t5_3b{FTCocip' | rev
```

### Flag:

> picoCTF{b3_5t111_mL|_<3_f2136893}

### Notes / Tips

- `fls` lists files from a disk image, `icat` extracts file contents by inode, `istat` shows inode metadata, and `blkcat` reads raw block data
- If a file looks empty/normal, check its allocated blocks and slack/adjacent raw data for hidden content
- This challenge is a classic disk forensics flow: enumerate -> extract -> inspect metadata -> read raw block -> decode


