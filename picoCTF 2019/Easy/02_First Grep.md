# First Grep

### Objective:

Can you find the flag in `file`? This would be really tedious to look through manually, something tells me there is a better way.

### Commands / Steps:

```bash
# Step 1: Get the file from the link, 'file'.
wget 'https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file'

# Step 2: View the contents of the file.
cat file
# We can see that it's too long.

# Step 3: Use grep to find the flag.
grep picoCTF file
```

### Flag:

> picoCTF{grep_is_good_to_find_things_5af9d829}

### Notes / Tips

- `grep [word] [filename]` --> Find a word in the file and print the lines containing that word.
    - `-i` --> Case insensitive


