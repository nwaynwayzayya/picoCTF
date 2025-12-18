# binhexa

### Description:

How well can you perfom basic binary operations?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".
Start searching for the flag here `nc titan.picoctf.net 63783`
Hint:

### Commands / Steps:

```bash
# Step 1: Connect to the given host and port using nc.
nc titan.picoctf.net 63783

# Step 2: After connecting, we will be given 6 questions relating to binary and then another one question relating to hexadecimal. 
# - Left shift (<<)
# - Right shift (>>)
# - AND (&)
# - OR (|)
# - Binary to hexadecimal conversion

# Step 3: Answer the questions correctly, and then we will be given the flag.
```

### Flag:

> picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d6f8047e}

### Notes / Tips

- `AND (&)`: 0&0=0, 0&1=0, 1&0=0, 1&1=1
- `OR (|)`: 0|0=0, 0|1=1, 1|0=1, 1|1=1
- `XOR (^)`: 0^0=0, 0^1=1, 1^0=1, 1^1=0
- `Left shift (<<)`: Shift bits left, add 0s on right
- `Right shift (>>)`: Shift bits right, add 0s on left
- `Hex conversion`: Group binary into 4-bit nibbles, convert to hex (0-9, A-F)


