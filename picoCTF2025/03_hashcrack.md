# hashcrack

### Description:

A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?
Additional details will be available after launching your challenge instance.
`Click 'Launch Instance'.`
Access the server using `nc verbal-sleep.picoctf.net 49559`

### Commands / Steps:

```bash
# Step 1: Connect to the server.
nc verbal-sleep.picoctf.net 49559
# Output:
# Welcome!! Looking For the Secret?
# We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
# Enter the password for identified hash:

# So here, we can see that we  are asked to reverse the hash given to us.

# Step 2: First, we use the 'Analyse hash' operation in 'Hash' tab on Cyberchef to identify what type of hash that is. 

# Step 3: After we get the type of hash, we can use online tools to reverse the hash. 

# Step 4: We will be asked to reverse the hash for three times and then, after we have answered all three questions correctly, we will get the flag.
```

### Flag:

> picoCTF{UseStr0nG_h@shEs_&PaSswDs!_4de57566}

### Notes / Tips

- Hash Identification: Use tools like `hashid` or online hash analyzers to identify hash types




