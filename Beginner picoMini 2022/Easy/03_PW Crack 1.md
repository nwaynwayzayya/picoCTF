# PW Crack 1

### Objective:

Can you crack the password to get the flag?
Download the password checker `here` and you'll need the encrypted `flag` in the same directory too.

### Commands / Steps:

```bash
# Step 1: Get the files
wget https://artifacts.picoctf.net/c/12/level1.py && wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc

# Step 2: We check the python script first to see what it is.
cat level1.py
# Inside the script, we find that the password is hardcoded: 8713

# Step 3: We run the python file and enter the password when prompted.
python level1.py
```

### Flag:

> picoCTF{545h_r1ng1ng_1b2fd683}

### Notes / Tips

- `cat [filename]` → Display the contents of a file.
- Always inspect scripts first — sometimes passwords or keys are hardcoded.
- Many beginner CTF challenges hide the solution in the code itself.



