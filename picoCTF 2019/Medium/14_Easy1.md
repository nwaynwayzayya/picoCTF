# Easy1

### Description:

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this?
We've given you the encrypted flag, key, and a table to help UFJKXQZQUNB with the key of SOLVECRYPTO. Can you use this `table` to solve it?.

### Commands / Steps:

```bash
# Step 1: Download the table from the description. 
wget [filelink]

# Step 2: It's a vigenere table, so we can use the given key to decode it in cyberchef.

# Step 3: Use the recipe named, Vigenere Decode, and enter the key 'SOLVECRYPTO' in the key field. Then put the encoded text in the input box and we will get the decoded text.
```

### Flag:

> picoCTF{CRYPTOISFUN}

### Notes / Tips

- **Vigenère cipher** uses a repeating key to encrypt text by shifting letters in the alphabet
- To decode: use the key repeatedly against each letter of the ciphertext (reverse the encryption process)
- **CyberChef** is an excellent online tool for crypto challenges - has built-in Vigenère decode function
- When given both ciphertext and key, decryption is straightforward - just apply the key cyclically 


