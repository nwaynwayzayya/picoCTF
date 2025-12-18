# interencdec

### Description:

Can you get the real meaning from this file.
Download the file `here`.
Hint: Engaging in various decoding processes is of utmost importance

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://artifacts.picoctf.net/c_titan/3/enc_flag

# Step 2: Check file content.
cat enc_flag
# Output: YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg==

# Step 3: The content of the file looks like 'base64', so we will decode it.
echo YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg== | base64 -d
# Output: b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='

# Step 4: It's still encoded (but with extra /b' and /' - python byte literal markers), so we will decode it for the second time excluding the trailing characters in the start and the end. 
echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ== | base64 -d
# Output: wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}

# Step 5: Now it looks like the usual flag but it seems like the characters are shifted, so we will decode it using an online Ceaser cipher decoder. Then, we will get the flag.
```

### Flag:

> picoCTF{caesar_d3cr9pt3d_b204adc6}

### Notes / Tips

- This challenge used two layers of Base64 encoding. The first decode revealed a Python bytes-literal `(b'...')` containing another Base64 string. Remove the `b'/'` wrapper or strip quotes before decoding again.
- Remember: Base64 is an encoding, not encryption — it just reversibly represents binary/text. Caesar is a simple substitution cipher — also trivial to brute force.


