# Mind your Ps and Qs

### Description:
In RSA, a small e value can be problematic, but what about N? Can you decrypt this?
`values`

Hint: Bits are expensive, I used only a little bit over 100 to save money

### Commands / Steps:

```bash
# Step 1: Download the `values` file and view its contents.
wget <filename>
cat values
# Decrypt my super sick RSA:
# c: 15341890103764929939105506004034128738090325640037083301857608662849501626260517
# n: 948406957756830799684818171639547165784816468744946013083947881743680617123566349
# e: 65537

# Step 2: Use the `dcode.fr` RSA cipher tool and enter `c`, `n`, and `e`. (link - https://www.dcode.fr/rsa-cipher)
}19ea7cd1_do0g_0n_N_11ams{FTCocip

# Step 3: Reverse the string to get the flag.
echo "}19ea7cd1_do0g_0n_N_11ams{FTCocip" | rev
```

### Flag:

> picoCTF{sma11_N_n0_g0od_1dc7ae91}

### Notes / Tips

- This is a weak-RSA challenge: the modulus is small enough that the ciphertext can be recovered with standard RSA tools
- Once the plaintext is decrypted, the result still needs to be reversed before it becomes the final flag
- Beginner RSA challenges often rely on solver tools, but the real lesson is that small key sizes make factoring `n` practical


