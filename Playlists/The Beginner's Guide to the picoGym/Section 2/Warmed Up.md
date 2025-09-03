# Warmed Up

### Objective:

What is 0x3D (base 16) in decimal (base 10)?

### Commands / Steps:

```bash
# Step 1: Convert to base 10
echo "ibase=16; 3D" | bc
# We don't need to put '0x' because bc already treats the input as hexadecimal when ibase-16
```

### Flag:

> picoCTF{61}

### Notes / Tips

- `bc` --> Command line calculator that can convert between bases.
- Alternative ways to solve -->
    - `echo $((0x3D))` --> Bash arithmetic
    - `printf "%d\n" 0x3D` --> Using printf


