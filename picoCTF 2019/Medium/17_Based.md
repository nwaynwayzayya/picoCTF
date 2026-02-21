# Based

### Description:

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?
Additional details will be available after launching your challenge instance.
Click "Launch Instance".
Connect with nc fickle-tempest.picoctf.net 63219.
Hint: I hear python can convert things.

### Commands / Steps:

```bash
# Step 1: Connect with nc fickle-tempest.picoctf.net 63219.

# Step 2: The challenges are conversion problems, so if we open cyberchef in another tab and answer the questions in time, we will get the flag.
Let us see how data is stored
table
Please give the 01110100 01100001 01100010 01101100 01100101 as a word.
...
you have 45 seconds.....

Input:
table
Please give me the  o154 o151 o155 o145 as a word.
Input:
lime
Please give me the 6c696d65 as a word.
Input:
lime
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_DF19A0E8}
```

### Flag:

> picoCTF{learning_about_converting_values_DF19A0E8}

### Notes / Tips

- **Binary (base 2)**: `01110100` = 116 = 't' (each group of 8 bits represents one ASCII character)
- **Octal (base 8)**: `o154` or `\154` = 108 = 'l' (prefix 'o' or backslash indicates octal)  
- **Hexadecimal (base 16)**: `6c` = 108 = 'l' (two hex digits per ASCII character)
- **Tools**: CyberChef "From Binary/Hex/Octal" recipes work perfectly for quick conversions under time pressure 


