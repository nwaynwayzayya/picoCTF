# 2Warm

### Objective:

Can you convert the number 42 (base 10) to binary (base 2)?

### Commands / Steps:

```bash
# Step 1: Convert from base 10(decimal) to base2(binary)
echo "obase=2; 42" | bc
```

### Flag:

> picoCTF{101010}

### Notes / Tips

- `bc` --> Command line calculator that can convert between bases.
- `ibase` → input base (tells bc what base your input numbers are in). Default is 10.
- `obase` → output base (tells bc what base to output the result in). Default is 10.
- Order matters: set `ibase` first if you are using a non-decimal input, then `obase`.
- For binary conversion: use `obase=2`.
- Example: hex 3D to binary → `echo "ibase=16; obase=2; 3D" | bc` → outputs 111101.


