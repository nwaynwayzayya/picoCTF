# ASCII Numbers

### Description:

Convert the following string of ASCII numbers into a readable string:
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x35 0x63 0x31 0x31 0x5f 0x6e 0x30 0x5f 0x71 0x75 0x33 0x35 0x37 0x31 0x30 0x6e 0x35 0x5f 0x31 0x6c 0x6c 0x5f 0x74 0x33 0x31 0x31 0x5f 0x79 0x33 0x5f 0x6e 0x30 0x5f 0x6c 0x31 0x33 0x35 0x5f 0x34 0x34 0x35 0x64 0x34 0x31 0x38 0x30 0x7d

### Commands / Steps:

```bash
# Step 1: The given strings are hexadecimal (base16), so we can just use an online converter like "cyberchef" to convert into a readable string. 

# Alternative: Remove the "0x" prefixes and convert hex to ASCII
echo "70 69 63 6f 43 54 46 7b 34 35 63 31 31 5f 6e 30 5f 71 75 33 35 37 31 30 6e 35 5f 31 6c 6c 5f 74 33 31 31 5f 79 33 5f 6e 30 5f 6c 31 33 35 5f 34 34 35 64 34 31 38 30 7d" | xxd -r -p

# Alternative method using Python:
python3 -c "print(bytes.fromhex('7069636f4354467b34356331315f6e305f717533353731306e355f316c6c5f743331315f79335f6e305f6c3133355f34343564343138307d').decode())"
```

### Flag:

> picoCTF{45c11_n0_qu35710n5_1ll_t311_y3_n0_l135_445d4180}

### Notes / Tips

- `Hex to ASCII`: Each 0x70 represents a hexadecimal byte that corresponds to an ASCII character
- `xxd -r -p`: Converts hex to binary (-r = reverse, -p = plain hex)
- Python method: `bytes.fromhex()` converts hex string to bytes, then decode to ASCII
- Online tools: CyberChef with "From Hex" operation works well
- Pattern: 0x70 = 'p', 0x69 = 'i', 0x63 = 'c', 0x6f = 'o' spells "pico"


