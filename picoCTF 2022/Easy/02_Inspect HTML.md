# Inspect HTML

### Description:

Can you get the flag?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
Can you get the flag?
Go to this `website` and see what you can discover.

### Commands / Steps:

```bash
# Step 1: We go to the website. There is no clue on the website, so we open the developer tools to inspect the page.

# Step 2: Search in the DOM, the flag is embedded in the HTML.
```

### Flag:

> picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}

### Notes / Tips

- The flag being present in the client-side HTML is an intentional vulnerability for this challenge: anything in the DOM or served HTML/JS can be read by anyone.

- In real applications, sensitive data (flags, secrets, credentials) must never be embedded client-side — always keep them server-side and protect with proper authentication/authorization.


