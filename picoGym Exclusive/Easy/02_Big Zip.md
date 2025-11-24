# Big Zip

### Objective:

Unzip this archive and find the flag.
`Download zip file`

### Commands / Steps:

```bash
# Step 1: Download the zip file. 
wget https://artifacts.picoctf.net/c/503/big-zip-files.zip

# Step 2: Unzip the file.
unzip big-zip-files.zip

# Step 3: We go into the 'big-zip-files' directory.
cd big-zip-files

# Step 4: There are a lot of files in the directory. Therefore, we can't look for flag in each file separately. We use recursive mode of grep.
grep -r "pico" .
```

### Flag:

> picoCTF{gr3p_15_m4g1c_ef8790dc}

### Notes / Tips

- `grep -r [keyword] .` → search recursively for a keyword in all files under current directory.
- The . (dot) represents the current directory in Linux.
    - So `grep -r "pico" .` means "search in this folder and all its subfolders."



