# Scan Surprise

### Description:

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
`challenge.zip`
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
The same files are accessible via SSH here:
`ssh -p 54226 ctf-player@atlas.picoctf.net`
Using the password 1db87a14. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Hint1: QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
Hint2: Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
Hint3: If you don't have access to a phone, you can also use zbar-tools to convert an image to text

### Commands / Steps:

```bash
# Step 1: Log into a remote machine using SSH and then enter 'yes' and a password to access it. 
ssh -p 54226 ctf-player@atlas.picoctf.net
# Outpur: A qr code image. 

# Step 2: Use your phone qr scanner to scan the code and the flag will be shown.
```

### Flag:

> picoCTF{p33k_@_b00_19eccd10}

### Notes / Tips

- The QR code is the flag itself — scanning reveals it.
- Alternatives:
    - We can also use zbar-tools as the hint suggest - `zbarimg flag.png`.
    - We can also use online decoders to get the flag - `https://zxing.org/w/decode.jspx`.



