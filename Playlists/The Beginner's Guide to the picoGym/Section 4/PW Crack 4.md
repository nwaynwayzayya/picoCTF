# PW Crack 4

### Objective:

Can you crack the password to get the flag?
Download the password checker `here` and you'll need the encrypted `flag` and the `hash` in the same directory too.
There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.

### Commands / Steps:

```bash
# Step 1: Get all the necerrary files. 
wget [link]

# Step 2: We check the python script first to see what it is.
cat level4.py
# We will need to modify the script to use the list of passwords in the dictionary.txt file.

# Step 3: We open the file and modify the script.
nano level5.py
# We modify the script. The script is below the notes.
# After modifying, we enter 'ctrl+ o' to write out and 'ctrl+x' to exit.

# Step 4: We run the python script.
python level5.py
```

### Flag:

> picoCTF{h45h_sl1ng1ng_36e992a6}

### Notes / Tips

- `nano [filename]` --> Text editor inside command line.

- Modified python script below:
```bash
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level5.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level5.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_5_pw_check():
    with open("dictionary.txt", "r") as f:
        for line in f:
            user_pw = line.strip()
            user_pw_hash = hash_pw(user_pw)

            if user_pw_hash == correct_pw_hash:
                print("Correct password: ", user_pw)
                print("Welcome back... your flag, user:")
                decryption = str_xor(flag_enc.decode(), user_pw)
                print(decryption)
                return

    print("That password is incorrect")


level_5_pw_check()
```


