# fixme2.py

### Description:

Fix the syntax error in the Python script to print the flag.
`Download Python script`

### Commands / Steps:

```bash
# Step 1: Download the file using 'wget'.
wget https://artifacts.picoctf.net/c/6/fixme2.py

# Step 2: Try running the python file. 
python fixme2.py
# Output:   File "/home/norelle-picoctf/fixme2.py", line 22
#     if flag = "":
#        ^^^^^^^^^
# SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?

# Step 3: See the contents of the file and check the syntax error.
cat fixme2.py
# Output: The python script. 
# We can find the error at the bottom of the script. 
#
# flag = str_xor(flag_enc, 'enkidu')
# # Check that flag is not empty
# if flag = "":
#   print('String XOR encountered a problem, quitting.')
# else:
#   print('That is correct! Here\'s your flag: ' + flag)
#
# The error is in "\if flag = "":\". The correct syntax is supposed to be "\if flag == "":\" because '=' means assigning values to a variable in python. 

# Step 4: Fix the error using nano text editor. 
nano fixme2.py
# After fixing, 'Ctrl+o' to save and 'Ctrl+x' to exit. 

# Step 5: Run the python file again and we will get the flag as an output. 
python fixme.py
```

### Flag:

> picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}

### Notes / Tips

- Remember:
    - = → assignment
    - == → comparison
- Always read the error message carefully — Python usually tells you exactly where the syntax error is.


