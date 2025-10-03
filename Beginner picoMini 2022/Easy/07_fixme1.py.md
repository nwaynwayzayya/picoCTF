# fixme1.py

### Description:

Fix the syntax error in this Python script to print the flag.
`Download Python script`

### Commands / Steps:

```bash
# Step 1: Download the file using wget. 
wget https://artifacts.picoctf.net/c/25/fixme1.py

# Step 2: Try running the python script.
python fixme1.py
# Output: 
#   File "/home/norelle-picoctf/fixme1.py", line 20
#     print('That is correct! Here\'s your flag: ' + flag)
# IndentationError: unexpected indent

# Step 3: There's an indentation error in the file so we fix it using the nano text editor.
nano fixme1.py
# In the bottom of the script, the script is written:
#
# flag = str_xor(flag_enc, 'enkidu')
#   print('That is correct! Here\'s your flag: ' + flag)
#
# Correct syntax: Delete the incorrect indentation before print statement.

# Step 4: After fixing the error, we save(Ctrl+o) the file and exit(Ctrl+x). Then, try running the file again and a flag will be printed.
python fixme1.py
```

### Flag:

> picoCTF{1nd3nt1ty_cr1515_6a476c8f}

### Notes / Tips

- Python is indentation-sensitive — extra or missing spaces at the beginning of a line can cause `IndentationError`.
- Always check the error message and the line number Python reports.


