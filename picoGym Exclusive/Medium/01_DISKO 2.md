# DISKO 2

### Description:

Can you find the flag in this disk image? The right one is Linux! One wrong step and its all gone!
Download the disk image `here`.
Hint: How can you extract/isolate a partition?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c/540/disko-2.dd.gz

# Step 2: Use gunzip to decompress the file.
gunzip disko-2.dd.gz

# Step 3: Let's check the strings of the file and grep the string "pico"
strings disko-2.dd.gz | grep pico
# There are a lot of different flags.

# Step 4: Let's check how many partitions the file has with 'fdisk' according to the hint.
fdisk -l disko-d.dd
# Disk disko-2.dd: 100 MiB, 104857600 bytes, 204800 sectors
# Units: sectors of 1 * 512 = 512 bytes
# Sector size (logical/physical): 512 bytes / 512 bytes
# I/O size (minimum/optimal): 512 bytes / 512 bytes
# Disklabel type: dos
# Disk identifier: 0x8ef8eaee

# Device      Boot Start    End Sectors Size Id Type
# disko-2.dd1       2048  53247   51200  25M 83 Linux
# disko-2.dd2      53248 118783   65536  32M  b W95 FAT32

# Step 5: There are two partitions and the first partition, Linux, will be the one we should be looking at according to the question. So, let's xtract the partition into an .img format.
dd if=disko-2.dd of=part1.img bs=512 skip=2048 count=51200

# Step 6: Then we'll extract only the strings from the image file and look for the flag.
strings part1.img | grep pico
```

### Flag:

> picoCTF{4_P4Rt_1t_i5_a93c3ba0}

### Notes / Tips

- `gunzip disko-2.dd.gz` - Decompresses gzipped file
    - Command: gunzip = GNU unzip
    - File: .gz = gzip compressed archive
- `fdisk -l disko-2.dd` - Lists partition table
    - Flag: `-l` = list partition tables
    - Purpose: Shows partition layout (start/end sectors, types, sizes)
- `dd if=disko-2.dd of=part1.img bs=512 skip=2048 count=51200` - Extracts partition
    - Flags:
        - `if` = input file
        - `of` = output file
        - `bs` = block size (512 bytes/sector)
        - `skip` = skip 2048 sectors to reach partition start
        - `count` = copy 51200 sectors (partition size)
        - Calculation: 2048 × 512 = partition offset in bytes
- `strings part1.img | grep pico` - Finds readable text
    - `strings` = extracts printable characters from binary files
    - `grep pico` = filters for flag pattern
    - Pipe `|` = sends output of one command to another



