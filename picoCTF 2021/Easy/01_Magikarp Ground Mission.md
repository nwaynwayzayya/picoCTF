# Magikarp Ground Mission

### Objective:

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88`
Additional details will be available after launching your challenge instance.

### Commands / Steps:

```bash
# Step 1: Launch the instance and connect via SSH.
ssh ctf-player@venus.picoctf.net -p 55947
# When prompted: Are you sure you want to continue connecting (yes/no/[fingerprint])?, type 'yes'.
# Then enter the password: ee388b88.

# Step 2: List files in the starting directory.
ls
# Files: 1of3.flag.txt  instructions-to-2of3.txt
cat 1of3.flag.txt && cat instructions-to-2of3.txt
# Output:
# picoCTF{xxsh_
# Next, go to the root of all things, more succinctly '/'.

# Step 3: Go to the root directory '/' and check its contents.
cd /
ls
# Among files: 2of3.flag.txt  instructions-to-3of3.txt
cat 2of3.flag.txt && cat instructions-to-3of3.txt
# Output:
# 0ut_0f_\/\/4t3r_
# Lastly, ctf-player, go home... more succinctly '~'.

# Step 4: Go to the home directory '~' and check files.
cd ~
ls
# Files: 3of3.flag.txt  drop-in
cat 3of3.flag.txt
# Output: 3ca613a1}
```

### Flag:

> picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}

### Notes / Tips

- `ssh user@host -p <port>` --> Connect to a remote machine using ssh on a given port.
- `/` --> Root directory
- `~` --> Home directory of the current user.
- `ls` --> List file and directories.
- `cat` --> Display the contents of a file. 
- `&&` → Runs the next command only if the previous one succeeds (useful for chaining).



