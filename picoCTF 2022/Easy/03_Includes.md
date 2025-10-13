# Includes

### Description:

Can you get the flag?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
Can you get the flag?
Go to this `website` and see what you can discover.

### Commands / Steps:

```bash
# Step 1: We go to the website. There's nothing suspicious on the page except for the 'Say hello' button.

# Step 2: Click the 'Say hello' button. When we click it, there's an alert saying 'This code is in a separate file!'. 

# Step 3: We inspect the page using developer tools. Search the DOM first. There's nothing suspicious.

# Step 4: The alert we got before says, 'This code is in a separate file!'. So, we go to 'Sources' tab to check the files. 

# Step 5: We can find 2 parts of the flag in the two separate files - styles.css and script.js.
```

### Flag:

> picoCTF{1nclu51v17y_1of2_f7w_2of2_6edef411}

### Notes / Tips

- This challenge demonstrates an intentional information-leak via included static assets. Anything served to the client (CSS, JS, images, etc.) can be read by an attacker.


