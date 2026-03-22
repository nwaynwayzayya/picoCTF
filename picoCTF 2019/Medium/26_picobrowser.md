# picobrowser

### Description:
This website can be rendered only by picobrowser, go and catch the flag!
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
`http://fickle-tempest.picoctf.net:57578`

Hint: You don't need to download a new web browser

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: When we enter the website, there's a button named "Flag" to click. When we click it, we can't get access to the flag because our browser isn't "picobrowser".

# Step 3: We can use "Burp Suite" to edit our "User-Agent". Use the "Proxy" tab and turn the "Intercept" on.

# Step 4: After that, we click the "Flag" button again. Our request header will be intercepted before the request is forwarded.
GET /flag HTTP/1.1
Host: fickle-tempest.picoctf.net:57578
Accept-Language: en-US,en;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://fickle-tempest.picoctf.net:57578/
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

# Step 5: Change the "User-Agent" line and forward it.
User-Agent: picobrowser

# Step 6: Forward the request and check the response page to get the flag.
```

### Flag:

> picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}

### Notes / Tips

- The server checks the `User-Agent` header, not your actual browser binary
- You can solve this with Burp, DevTools, or `curl` by spoofing the same header
- Example with curl: `curl -H "User-Agent: picobrowser" http://fickle-tempest.picoctf.net:57578/flag`


