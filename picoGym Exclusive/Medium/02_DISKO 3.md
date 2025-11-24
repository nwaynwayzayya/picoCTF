# DISKO 3

### Description:

Can you find the flag in this disk image? This time, its not as plain as you think it is!
Download the disk image `here`.
Hint: How will you search and extract files in a partition?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c/543/disko-3.dd.gz

# Step 2: Use gunzip to decompress the file.
gunzip disko-3.dd.gz

# Step 3: Check to see if there's anything we can find with strings.
strings disko-3.dd | grep pico
# pico desta partici
# Description-it.UTF-8: Utilizzo tipico di questa partizione:
# pico desta parti
# Description-it.UTF-8: Utilizzo tipico:
# pico:
# Aug 30 01:59:37 debootstrap: update-alternatives: using /bin/nano to provide /usr/bin/pico (pico) in auto mode
# Aug 30 02:00:42 in-target:   mailx | mailutils snmptrapd libttspico-utils espeak mbrola
# MESSAGE=[system] Activating via systemd: service name='org.bluez' unit='dbus-org.bluez.service' requested by ':1.81' (uid=1000 pid=12105 comm="/usr/share/code/code Desktop/picoctf-2025")
# MESSAGE=[system] Activating via systemd: service name='org.bluez' unit='dbus-org.bluez.service' requested by ':1.66' (uid=1000 pid=43129 comm="/usr/share/code/code Desktop/picoctf-2025")
# MESSAGE=[system] Activating via systemd: service name='org.bluez' unit='dbus-org.bluez.service' requested by ':1.65' (uid=1000 pid=2141 comm="/usr/share/code/code Desktop/picoctf-2025")
# MESSAGE=[system] Activating via systemd: service name='org.bluez' unit='dbus-org.bluez.service' requested by ':1.65' (uid=1000 pid=2584 comm="/usr/share/code/code Desktop/picoctf-2025")

# Step 4: So there are files in it which we can extract. 
binwalk -e disko-3.dd

# Step 5: Then check the directory and go into the directory where the extracted files are saved.
ls
cd _disko-3.dd.extracted
ls  # Check which files are in the directory.
# 1166A00  1276400  128A200     12A1C00  12B1400  12B1A00  12DF200  1304400  131EC00  13F6600  flag
# 1170A00  1289E00  128A200.xz  12A3600  12B1800  12B2000  12FB400  1306600  13A5C00  13FB000
# The file 'flag' might include the flag so we view the contents of the file.
cat flag
```

### Flag:

> picoCTF{n3v3r_z1p_2_h1d3_654235e0}

### Notes / Tips

- `gunzip disko-3.dd.gz` - Decompresses gzipped disk image file
- `strings disko-3.dd | grep pico` - Searches for readable text containing "pico"
- `binwalk -e disko-3.dd` - Extracts embedded files from disk image
    - `-e` = extract embedded files
- Creates automatic directory: `_disko-3.dd.extracted/`
- Binwalk's default naming: `_filename.extracted`
- File Carving: Recovers files by scanning for known file headers/footers


