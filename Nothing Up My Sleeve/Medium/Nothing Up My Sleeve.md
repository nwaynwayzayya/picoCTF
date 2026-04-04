# Nothing Up My Sleeve

### Description:
Let's check that your internet connection is working. This flag is 'in-the-clear', I promise!
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
Download `flag.txt`

Hint: If all you had access to was a shell, you could use wget to download the file at the URL above!

### Commands / Steps:

```bash
# Step 1: Download the file using wget command.
wget [filelink]

# Step 2: View the file contents.
cat flag.txt
```

### Flag:

> picoCTF{c0ngr4ts_0n_y0ur_s4n1ty}

### Notes / Tips

- This is a basic connectivity and file retrieval sanity-check challenge
- `wget <url>` downloads files directly from a URL in terminal-only environments
- After downloading, use `cat flag.txt` to quickly read plain-text flags
- If `wget` is unavailable, use `curl -O <url>` as an alternative


