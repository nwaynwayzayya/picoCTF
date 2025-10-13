# repetitions

### Description:

Can you make sense of this file?
Download the file `here`.
Hint: Multiple decoding is always good.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c/471/enc_flag

# Step 2: Check the contents of the file first.
cat enc_flag
# VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
# RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
# MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
# VkpEVGxaYVdFMVhSbFpSV0VKWVZGVmtNRTVHV2tWU2JYUlVDbUpXV25sVWJGcHZWbGRHZEdWRlZs
# aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

# Step 3: The challenged is tagged as base64, so we will try decoding the file with base64 first.
base64 -d enc_flag
# VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
# bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
# MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlZRWEJYVFVkME5GWkVSbXRUCmJWWnlUbFpvVldGdGVFVlhi
# bTkzVDFWT2JsQlVNRXNLCg==
# Note: It's not fully decoded yet, but it got shorter.

# Step 4: The contents of the file got shorter if we decode it using base64. And according to the hint, there's a change that we will get the flag if we try decoding multiple times.
base64 -d enc_flag > first
# We decode it and save the result into a file. We will do it multiple times until we get the flag.

```

### Flag:

> picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_9b59b35c}

### Notes / Tips

- Some CTF challenges use multiple layers of encoding (like `Base64`, `hex`, or `rot13`).

- Keep decoding until the output looks readable or you find a flag pattern `(picoCTF{...})`.


