# Bases

### Objective:

What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

### Commands / Steps:

```bash
# This might be base64.
# Step 1: Echo the "bDNhcm5fdGgzX3IwcDM1" into a file.
echo "bDNhcm5fdGgzX3IwcDM1" > base64file

# Step 2: Decode base64
base64 -d base64file
# Output: l3arn_th3_r0p35
```

### Flag:

> picoCTF{l3arn_th3_r0p35}

### Notes / Tips

- Alternative solution: We don't need to make a file because it's only one line of string.
    - `echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d`
- `base64 -d [filename]` --> Decode the file.
- Base64 encodes binary data into text using 64 ASCII characters.
- `bc` cannot decode Base64 because it only handles numeric bases.


