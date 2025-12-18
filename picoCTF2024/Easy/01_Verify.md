# Verify

### Description:

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
`ssh -p 53649 ctf-player@rhea.picoctf.net`
Using the password 6abf4a82. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Checksum: b09c99c555e2b39a7e97849181e8996bc6a62501f0149c32447d8e65e205d6d2
To decrypt the file once you've verified the hash, run `./decrypt.sh files/<file>`.
Hint1: Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.
Hint2: You can create a SHA checksum of a file with `sha256sum <file>` or all files in a directory with `sha256sum <directory>/*`.
Hint3: Remember you can pipe the output of one command to another with `|`. Try practicing with the 'First Grep' challenge if you're stuck!


### Commands / Steps:

```bash
# Step 1: Log into a remote machine using SSH and then enter 'yes' and a password to access it. 
ssh -p 53649 ctf-player@rhea.picoctf.net

# Step 2: Check the files in the directory.
ls

# Step 3: Create a SHA checksum of all the files in the 'files' directory and use grep to find the correct file with the same hash value.
sha256sum files/* | grep "b09c99c555e2b39a7e97849181e8996bc6a62501f0149c32447d8e65e205d6d2"
# Output: b09c99c555e2b39a7e97849181e8996bc6a62501f0149c32447d8e65e205d6d2  files/451fd69b

# Step 4: Decrypt the file using the given script. 
./decrypt.sh files/451fd69b
# The output will be the flag we're looking for. 
```

### Flag:

> picoCTF{trust_but_verify_451fd69b}

### Notes / Tips

- Always verify checksums before decrypting/downloading sensitive files — `checksums` let you confirm file integrity and origin.


