# PW Crack 2

### Objective:

Can you crack the password to get the flag?
Download the password checker here and you'll need the encrypted flag in the same directory too.

### Commands / Steps:

```bash
# Step 1: Get the files
wget https://artifacts.picoctf.net/c/14/level2.py && wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc

# Step 2: We check the python script first to see what it is.
cat level2.py
# Inside the script, we find that the password is in hex(base16) format.
#  if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):

# Step 3: We convert the password from base16.
printf "\x34\x65\x63\x39\n"
# Output: 4ec9

# Step 4: We run the python script and entered the password we got in step 3 when prompted.
python level2.py
```

### Flag:

> picoCTF{tr45h_51ng1ng_9701e681}

### Notes / Tips

- `printf "\xHH"` → Converts hex values to ASCII characters.
- Alternative: `echo $((0x34))` → Gives decimal (useful for ASCII codes).
- `xxd -r -p` can also decode hex strings directly.
- Always check Python scripts for hardcoded passwords or conditions.



