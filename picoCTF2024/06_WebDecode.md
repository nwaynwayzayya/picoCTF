# WebDecode

### Description:

Do you know how to use the web inspector?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
Start searching `here` to find the flag
Hint1: Use the web inspector on other files included by the web page.
Hint2: The flag may or may not be encoded.

### Commands / Steps:

```bash
# Step 1: Go to the website and navigate a little to find anything suspicious. 

# Step 2: When navigating the page, "About", we are hinted, "Try inspecting the page!! You might find it there". 

# Step 3: We open the developer tools and inspect that "About" page. We go to the "Sources" tab of dev tools, and inspect the about.html file. 

# Step 4: While reading the html codes, we found the suspicious line of code. 
### <section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9">
### Here, 'notify_true' doesn't look like a custom HTML attribute and 'cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9' looks like a base64-encoded text.

# Step 5: We decode the base64-encoded text to see if it's a flag.
echo "cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMTBmOTM3NmZ9" | base64 -d
# Output is the flag. 
```

### Flag:

> picoCTF{web_succ3ssfully_d3c0ded_10f9376f}

### Notes / Tips

- Always check the “Sources” tab in DevTools for additional HTML files or scripts — flags in web CTFs are often hidden there rather than directly in the visible page.

- The string format (cGljb0NUR...) is a clear indicator of Base64 encoding — look for patterns ending in =, or strings with uppercase, lowercase, numbers, and /+.

- You can also use online Base64 decoders (like CyberChef) if command line tools are unavailable.


