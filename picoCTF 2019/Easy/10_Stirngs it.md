# Strings it

### Objective:

Can you find the flag in `file` without running it?

### Commands / Steps:

```bash
# Step 1: We get the file from the link 'file'.
wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings

# Step 2: View the contents of a file first.
cat strings
# The file is too big for us to read.

# Step 3: Use 'strings' command to get the sequence of readable characters.
strings strings
# There are a lot of lines and printable characters

# Step 4: Use piping and grep command to get the flag.
strings strings | grep picoCTF
```

### Flag:

> picoCTF{5tRIng5_1T_d66c7bb7}

### Notes / Tips

- `strings [filename]` --> Prints the sequence of printable characters in a file 
- `[first command] | [second command]` --> Sends the output of the first command as an input to the second command
- `grep [word]` --> Find a word and print the lines containing that word.



