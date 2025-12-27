# caesar

### Description:

Decrypt this message.
Message: message
Hint: Caesar cipher tutorial

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filelink]

# Step 2: View the encrypted message.
cat data.enc
# Output: picoCTF{gvswwmrkxlivyfmgsrfuppobuf}

# Step 3: Since the hint is the caesar cipher, we can just use cyberchef or other cipher tools to rotate the texts until we get the possible flag.
```

### Flag:

> picoCTF{crossingtherubiconbqllkxqb}

### Notes / Tips

- `Caesar Cipher`: Simple substitution cipher where each letter is shifted a fixed number of positions
- `ROT13`: Special case of Caesar cipher with 13-character shift (reversible)
- `Brute Force`: Only 25 possible shifts for lowercase letters (ROT1 to ROT25)
- `Pattern Recognition`: Look for English words in decrypted text




