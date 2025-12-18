# Commitment Issues

### Description:

I accidentally wrote the flag down. Good thing I deleted it!
You download the challenge files here:
`challenge.zip`
Hint: Version control can help you recover files if you change or lose them!

### Commands / Steps:

```bash
# Step 1: Download the zip file.
wget https://artifacts.picoctf.net/c_titan/139/challenge.zip

# Step 2: Unzip the file. 
unzip challenge.zip

# Step 3: Go into the directory.
cd drop-in

# Step 4: Check the past git commits. 
git log --oneline
# 144fdc4 (HEAD -> master) remove sensitive info
# 7d3aa55 create flag
## The above shows that there were two commits.

# Step 5: 'create flag' seems suspicious, so we will go back to the older commit and check it.
git checkout 7d3aa55

# Step 6: Check files in this state.
ls
# message.txt -- only one file here.

# Step 7: Check file content.
cat message.txt
# We will get a flag from this file.
```

### Flag:

> picoCTF{s@n1t1z3_be3dd3da}

### Notes / Tips

- Even if someone “deletes” sensitive data in Git, it can still be recovered from history unless the commit is permanently removed (e.g., via `git filter-branch` or `git rebase` with history rewrite).


