# Scavenger Hunt

### Objective:

There is some interesting information hidden around this site `http://mercury.picoctf.net:55079/`. Can you find it?
Hint: You should have enough hints to find the files, don't run a brute forcer.

### Commands / Steps:

```bash
# Step 1: Vist the link that's given in the description.

# Step 2: First, we inspect the pages. 

# Step 3: Then, in the source tab, we can find the part 1 of the flag in the index.html.

# Step 4: The part 2 of the flag is in the mycss.css file.

# Step 5: The clue to part 3 is given in myjs.js. "/* How can I keep Google from indexing my website? */". This means that the flag is in "http://mercury.picoctf.net:55079/robots.txt".

# Step 6: The next clue to part 4 says that it's an apache server. So, we can try some files we can look up where there are hidden files. 

# Step 7: We can find part 4 in ".htaccess" and following the clue after part 4 - " I love making websites on my Mac, I can Store a lot of information there.", we can find the last clue in ".DS_Store".
```

### Flag:

> picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}

### Notes / Tips

- `robots.txt` --> Tells search engines which paths NOT to crawl — often hides “secret” directories.
- `.htaccess` --> Apache config file — might reveal flags, redirects, or secret folders.
- `.DS_Store` --> macOS folder metadata — reveals file names in the directory.

