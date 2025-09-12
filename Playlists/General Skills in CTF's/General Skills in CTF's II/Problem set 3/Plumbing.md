# Plumbing

### Objective:

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291.`

### Commands / Steps:

```bash
# Step 1: We use netcat to connect to 'jupiter.challenges.picoctf.org 14291'.
nc jupiter.challenges.picoctf.org 14291
# This prints a lot of output to your terminal.

# Step 2: We use pipe and grep to look for the flag.
nc jupiter.challenges.picoctf.org 14291 | grep pico
```

### Flag:

> picoCTF{digital_plumb3r_ea8bfec7}

### Notes / Tips

- `nc <host> <port>` --> Open a tcp connection and stream program output in your terminal.
- `<first command> | <second command>` --> Used when we want to send the output of the first command to the second command as an input.
- `grep <pattern>` --> Finds pattern from the output.


