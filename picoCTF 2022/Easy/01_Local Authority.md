# Local Authority

### Description:

Can you get the flag?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
Can you get the flag?
Go to this `website` and see what you can discover.

### Commands / Steps:

```bash
# Step 1: We go to the website. 

# Step 2: In the website, we can see a log in page. We inspect the website using developer tools.

# Step 3: We try logging in with random username and password. It would be incorrect of course, and it will show us "Log In Failed" screen. However, in the element tab of dev tools, we can look through the DOM and scripts:
#     <script src="secure.js"></script>
    
#     <p id='msg'></p>
    
#     <form hidden action="admin.php" method="post" id="hiddenAdminForm">
#       <input type="text" name="hash" required id="adminFormHash">
#     </form>

# Step 4: We will try going to "Sources" tab and find 'secure.js' file. There, we get the username and password for admin. 

# Step 5: We enter the admin's credentials and login. Then, we will get the flag. 
```

### Flag:

> picoCTF{j5_15_7r4n5p4r3n7_a8788e61}

### Notes / Tips

- This is a classic case of sensitive data stored client-side. Secrets (passwords, tokens, flags) must never be included in HTML/JS served to users. Anything in client-side code can be read by anyone with a browser.

- Safer alternatives: keep credentials and flag access server-side only, authenticate/authorize requests on the server, and never hard-code secrets into client JavaScript.

- When testing similar challenges, always check the Sources / static files and any hidden form fields — sometimes the challenge hides useful data there.


