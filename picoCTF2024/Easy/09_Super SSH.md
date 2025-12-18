# Super SSH

### Objective:

Using a Secure Shell (SSH) is going to be pretty important.
Can you ssh as ctf-player to titan.picoctf.net at port 52834 to get the flag?
You'll also need the password 1db87a14. If asked, accept the fingerprint with yes.

### Commands / Steps:

```bash
# Step 1: Connect to the server
ssh ctf-player@titan.picoctf.net -p 52834

# Step 2: When prompted, enter 'yes' to continue connecting.
yes

# Step 3: Enter the password
1db87a14        
# The password won't be visible when you're typing.
# The flag will be revealed after connecting.
```

### Flag:

> picoCTF{s3cur3_c0nn3ct10n_45a48857}

### Notes / Tips

- `ssh username@hostname -p [port number]` --> Connects to a remote server using Secure Shell (encrypted connection)