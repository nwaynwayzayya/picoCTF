# PW Crack 3

### Objective:

Can you crack the password to get the flag?
Download the password checker `here` and you'll need the encrypted `flag` and the `hash` in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

### Commands / Steps:

```bash
# Step 1: Get all the necerrary files. 
wget [link]

# Step 2: We check the python script first to see what it is.
cat level3.py
# Inside the script, we find that the password is a list.
# The strings below are 7 possibilities for the correct password. 
# (Only 1 is correct)
# pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
# So we can modify level3.py to check the password with the list with a for loop.

# Step 3: We open the file and modify the script.
nano level3.py
# We modify the script. The script below the notes.
# After modifying, we enter 'ctrl+ o' to write out and 'ctrl+x' to exit.

# Step 4: We run the python script.
python level3.py
```

### Flag:

> picoCTF{m45h_fl1ng1ng_cd6ed2eb}

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

# Move the password list here
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

def level_3_pw_check():
# Make a for loop here
    for user_pw in pos_pw_list: 
        user_pw_hash = hash_pw(user_pw)
    
        if( user_pw_hash == correct_pw_hash ):
            print("Correct password:",user_pw)
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
# pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]
```


