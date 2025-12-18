# Bookmarklet

### Description:

Why search for the flag when I can make a bookmarklet to print it for me?
Additional details will be available after launching your challenge instance.
`Click Launch Instance.`
Browse `here`, and find the flag!

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: There's a bookmarklet(javascript code) that's given to us.
# javascript:(function() {
#     var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÒËÉ§©í";
#     var key = "picoctf";
#     var decryptedFlag = "";
#     for (var i = 0; i < encryptedFlag.length; i++) {
#         decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
#     }
#     alert(decryptedFlag);
# })();

# Step 3: Let's try running that in Developer Tools. There's a tab called 'Console' where we can run the javascript directly in the browser. We copy the bookmarklet and run the javascript code. Then, we will get an alert box with the flag.
```

### Flag:

> picoCTF{p@g3_turn3r_6bbf8953}

### Notes / Tips

- # Bookmarklet

### Description:

Why search for the flag when I can make a bookmarklet to print it for me?
Additional details will be available after launching your challenge instance.
`Click Launch Instance.`
Browse `here`, and find the flag!

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: There's a bookmarklet(javascript code) that's given to us.
# javascript:(function() {
#     var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÒËÉ§©í";
#     var key = "picoctf";
#     var decryptedFlag = "";
#     for (var i = 0; i < encryptedFlag.length; i++) {
#         decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
#     }
#     alert(decryptedFlag);
# })();

# Step 3: Let's try running that in Developer Tools. There's a tab called 'Console' where we can run the javascript directly in the browser. We copy the bookmarklet and run the javascript code. Then, we will get the flag.
```

### Flag:

> picoCTF{p@g3_turn3r_6bbf8953}

### Notes / Tips

- # Bookmarklet

### Description:

Why search for the flag when I can make a bookmarklet to print it for me?
Additional details will be available after launching your challenge instance.
`Click Launch Instance.`
Browse `here`, and find the flag!

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: There's a bookmarklet(javascript code) that's given to us.
# javascript:(function() {
#     var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÒËÉ§©í";
#     var key = "picoctf";
#     var decryptedFlag = "";
#     for (var i = 0; i < encryptedFlag.length; i++) {
#         decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
#     }
#     alert(decryptedFlag);
# })();

# Step 3: Let's try running that in Developer Tools. There's a tab called 'Console' where we can run the javascript directly in the browser. We copy the bookmarklet and run the javascript code. Then, we will get the flag.
```

### Flag:

> picoCTF{p@g3_turn3r_6bbf8953}

### Notes / Tips

- `Bookmarklets` are JavaScript code snippets that can be saved as browser bookmarks
- `Console tab` → Where you can run JavaScript code directly in the browser








