# endianness

### Description:

Know of little and big endian?
`Source`
Additional details will be available after launching your challenge instance.
Click "Launch Instance".

`nc titan.picoctf.net 52682`

### Commands / Steps:

```bash
# Step 1: Connect to the remote machine.
nc titan.picoctf.net 52682
# Output: 
# Welcome to the Endian CTF!
# You need to find both the little endian and big endian representations of a word.
# If you get both correct, you will receive the flag.
# Word: ejeys
# Enter the Little Endian representation:

# Step 2: First, we find the hex representation of the word given which is "65 6a 65 79 73". That value is big endian. The little endian is the reverse order of it. 
# We enter the reversed order hex (without spaces).
7379656a65
# Then, we are asked the big endian representation of it which we already have.

# Step 3: Enter the big endian representation (without spaces).
656a657973
# Then, we will get the flag.
```

### Flag:

> picoCTF{3ndi4n_sw4p_su33ess_25c5f083}

### Notes / Tips

- Big-endian hex = the direct byte-by-byte hex of the string.
- Little-endian hex = reverse the sequence of bytes (each byte is two hex characters); do not reverse the characters inside each byte.


