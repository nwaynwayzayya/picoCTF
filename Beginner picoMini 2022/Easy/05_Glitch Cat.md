# Glitch Cat

### Description:

Our flag printing service has started glitching!
`$ nc saturn.picoctf.net 64819`

### Commands / Steps:

```bash
# Step 1: Connect to the host using nc.
nc saturn.picoctf.net 64819
# Output: 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'

# Step 2: We can use 'Ctrl+c' to close the connection and return to the prompt. We can use python to change that base16 into ASCII.
python -c "print('picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}')"
# Then, we will get the flag.
```

### Flag:

> picoCTF{gl17ch_m3_n07_a4392d2e}

### Notes / Tips

- Alternative way to solve:
    - `nc saturn.picoctf.net 64819 | python -c "import sys; print(eval(sys.stdin.read()))"`
    - This reads the expression sent by the service and evaluates it in Python, producing the decoded flag directly.

- The 0x.. notation is hexadecimal (base 16). For example, 0x61 = decimal 97 = 'a'.

- chr(0x61) converts the hex code to its ASCII character. The challenge printed the flag as a Python expression combining string literals and chr() calls.


