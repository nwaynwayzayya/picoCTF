# Blame Game

### Description:

Someone's commits seems to be preventing the program from working. Who is it?
You can download the challenge files here:
`challenge.zip`
Hint: In collaborative projects, many users can make many changes. How can you see the changes within one file?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c_titan/159/challenge.zip

# Step 2: Unzip the zip file.
unzip challenge.zip

# Step 3: Go into the directory that the zip file was unzipped in. 
cd drop-in/

# Step 4: Check the files in the directory.
ls
# message.py

# Step 5: Let's check the logs of the file according to the hint.
git log message.py
# You will find the flag afterwards.
```

### Flag:

> picoCTF{@sk_th3_1nt3rn_81e716ff}

### Notes / Tips

- `git log <filename>` → Shows commit history for a specific file
- `git blame <filename>` → Shows who last modified each line of a file (#Alternative way)




