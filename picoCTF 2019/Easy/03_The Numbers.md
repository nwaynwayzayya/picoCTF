# The Numbers

### Objective:

The `numbers...` what do they mean?

### Commands / Steps:

```bash
# Step 1: We download the file.
wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png

# Step 2: We open the png and see '16 9 3 15 3 20 6 {20 8 5 14 21 13 2 5 18 19 13 1 19 15 14}'.
# Recognize that numbers correspond to letters (A=1, B=2, ..., Z=26).
# We write a Python script to automate the decoding.
nano script.py
# script.py
# import string
#
# flag = ''
# for i in [16, 9, 3, 15, 3, 20, 6, 20, 8, 5, 14, 21, 13, 2, 5, 18, 19, 13, 1, 19, 15, 14]:
#     flag += string.ascii_uppercase[i-1]
#
# print(flag)

# Step 3: Run the Python script to decode.
python3 script.py
# Output: PICOCTFTHENUMBERSMASON
# Add curly braces after "PICOCTF".
```

### Flag:

> PICOCTF{THENUMBERSMASON}

### Notes / Tips

- `A1Z26 Cipher`: This is the name of the cipher where A=1, B=2, ..., Z=26.
- `string.ascii_uppercase` gives a string of all uppercase letters: `"ABCDEFGHIJKLMNOPQRSTUVWXYZ"`.
- `i-1` is used because Python strings are 0-indexed (so `string.ascii_uppercase[0]` = 'A').
- You can use a one-liner to avoid writing a script:
    ```bash
    python3 -c "import string; nums=[16,9,3,15,3,20,6,20,8,5,14,21,13,2,5,18,19,13,1,19,15,14]; print(''.join(string.ascii_uppercase[i-1] for i in nums))"
    ```



