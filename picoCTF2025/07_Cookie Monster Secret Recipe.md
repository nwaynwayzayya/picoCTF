# Cookie Monster Secret Recipe  

### Description:

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".`
You can access the Cookie Monster `here` and good luck

### Commands / Steps:

```bash
# Step 1: Visit the launched site by clicking the link profived after launching the instance.

# Step 2: First, we are greeted with a login site. We don't have any clues yet, so let's try any credential we want and click login. 
# Output: 
# Cookie Monster says: 'Me no need password. Me just need cookies!'
# Hint: Have you checked your cookies lately? 

# Step 3: The hint says something about the cookies, so let's check the cookies by inspecting the page. Right click the page and click "Inspect".

# Step 4: Go to the "Application" tab and check the cookies.

# Step 5: We see one cookie with the value of "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzczMTEwRUQxfQ==". 

# Step 6: Seeing it ends with '==', it's likely in base64 form. We'll use the Cyberchef or any other online tools to decode it. Then, we'll get the flag. 
```

### Flag:

> picoCTF{c00k1e_m0nster_l0ves_c00kies_73110ED1}

### Notes / Tips

- `Base64 Indicators`: Strings ending with = or == are typically base64 encoded
- `No Credentials Needed`: The challenge explicitly states passwords aren't required




