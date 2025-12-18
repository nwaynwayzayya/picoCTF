# Collaborative Development

### Description:

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
You can download the challenge files here:
`challenge.zip`

Hint: git branch -a will let you see available branches

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c_titan/178/challenge.zip

# Step 2: Unzip the file.
unzip challenge.zip

# Step 3: Navigate into the directory.
cd drop-in/

# Step 4: Check available branches.
git branch -a
#   feature/part-1
#   feature/part-2
#   feature/part-3
# * main

# Step 5: We will visit the different branches and find the parts of the flag.py in those branches. We will get the flag if we combine the parts of the flag from those three files.
git checkout feature/part-1
cat flag.py

git checkout feature/part-2  
cat flag.py

git checkout feature/part-3
cat flag.py
```

### Flag:

> picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}

### Notes / Tips

- `git branch -a` → List all available branches (both local and remote)
- `git checkout <branch-name>` → Switch between different branches
- `cat flag.py` → View the contents of the flag.py file in each branch


