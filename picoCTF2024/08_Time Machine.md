# Time Machine

### Description:

What was I last working on? I remember writing a note to help me remember...
You can download the challenge files here:
`challenge.zip`

### Commands / Steps:

```bash
# Step 1: Download the zip file. 
wget https://artifacts.picoctf.net/c_titan/163/challenge.zip

# Step 2: Unzip the file. 
unzip challenge.zip

# Step 3: Check the folders and files after.
ls

# Step 4: Search for flag using grep recursively.
grep -r "pico" drop-in/
# Output: The flag is in git commit messages.
# drop-in/.git/COMMIT_EDITMSG:picoCTF{t1m3m@ch1n3_88c35e3b}
# drop-in/.git/logs/HEAD:0000000000000000000000000000000000000000 e65fedb3a72a16c577f4b17023b63997134b307d picoCTF <ops@picoctf.com> 1710202049 +0000     commit (initial): picoCTF{t1m3m@ch1n3_88c35e3b}
# drop-in/.git/logs/refs/heads/master:0000000000000000000000000000000000000000 e65fedb3a72a16c577f4b17023b63997134b307d picoCTF <ops@picoctf.com> 1710202049 +0000        commit (initial): picoCTF{t1m3m@ch1n3_88c35e3b}
```

### Flag:

> picoCTF{t1m3m@ch1n3_88c35e3b}

### Notes / Tips

- Using `grep -r` or find recursively is a good strategy to search through multiple files and folders.
- This challenge is an example of `git forensics`: understanding how version control metadata can reveal information.


