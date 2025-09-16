# Let's warm up

### Objective:

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

### Commands / Steps:

```bash
# Step 1: We can use python to convert hex directly to ASCII.
python3 -c "print(chr(0x70))"
# Output: p
```

### Flag:

> picoCTF{p}

### Notes / Tips

- Prefix 0x means the number is in hexadecimal (base 16).
- Useful conversions:
    - Hex → Decimal: `echo $((0x70))`
    - Decimal → ASCII: `python3 -c "print(chr(112))"`
    - Hex → ASCII directly: `python3 -c "print(chr(0x70))"`
    - `chr()` converts a number into its corresponding ASCII/Unicode character.