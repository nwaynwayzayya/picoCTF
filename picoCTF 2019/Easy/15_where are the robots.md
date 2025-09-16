# where are the robots

### Objective:

Can you find the robots? https://jupiter.challenges.picoctf.org/problem/56830/ (link) or http://jupiter.challenges.picoctf.org:56830

### Commands / Steps:

```bash
# Step 1: Open the link in the browser.

# Step 2: The hints says 'What part of the website could tell you where the creator doesn't want you to look?'.
# In websites, we can find robots.txt which is an instruction file for web crawlers which part of a website they should or should not visit.

# Step 3: We visit robots.txt subdomain. 
http://jupiter.challenges.picoctf.org:56830/robots.txt
# Output: 
# User-agent: *
# Disallow: /1bb4c.html

# Step 4: We visit the disallowed path.
http://jupiter.challenges.picoctf.org:56830/1bb4c.html
# We get the flag here.
```

### Flag:

> picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

### Notes / Tips

- `robot.txt` --> A file used by websites to give instructions to web crawlers about which pages or directories should not be indexed.
- In CTFs, always check for /robots.txt — it often hides disallowed paths containing flags.


