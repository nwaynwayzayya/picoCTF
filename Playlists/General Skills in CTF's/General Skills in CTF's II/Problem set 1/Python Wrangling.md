# Python Wrangling

### Objective:

Python scripts are invoked kind of like programs in the Terminal... Can you run this `Python script` using `this password` to get `the flag`?

### Commands / Steps:

```bash
# Step 1: Get the files
wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/ende.py
wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/pw.txt
wget https://mercury.picoctf.net/static/2ac2139344d2e734d5d638ac928f1a8d/flag.txt.en

# Step 2: We try running the python script.
python ende.py
# Output: 
# Usage: ende.py (-e/-d) [file]

# Step 3: We run the file according to the instriction.
python ende.py -d flag.txt.en
# (Enter the password from pw.txt when prompted)
# Alternative: python ende.py -d flag.txt.en < pw.txt
```

### Flag:

> picoCTF{4p0110_1n_7h3_h0us3_68f88f93}

### Notes / Tips

- `python [filename]` --> Run a python script.
- If a program asks for input (like a password), you can type it manually or redirect input from a file using `< filename`.


