# Binary Search 

### Description:
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!
You can download the challenge files here:
`challenge.zip`
Additional details will be available after launching your challenge instance.
`ssh -p 49933 ctf-player@atlas.picoctf.net`
Using the password f3b61b38. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!


### Commands / Steps:

```bash
# Step 1: # Step 1: Log into a remote machine using SSH and then enter 'yes' and a password to access it. 
ssh -p 49933 ctf-player@atlas.picoctf.net

# Step 2: The challenge is simple binary search. So, we can easily apply the binary search strategy.
#   1. Start with the middle number: 500
#   2. If the message says “higher”, move to the midpoint of 500–1000 → 750
#   3. If “lower”, move to midpoint of 1–500 → 250
#   4. Continue halving the range each time until you find the number.

# Step 3: The flag will be displayed after a correct guess.
```

### Flag:

> picoCTF{g00d_gu355_6dcfb67c}

### Notes / Tips

- Binary search always halves the range — that’s why it’s so efficient.
- If you forget the logic:
    - Start in the middle.
    - Follow “higher” or “lower” feedback.
    - Repeat until you find the target.


