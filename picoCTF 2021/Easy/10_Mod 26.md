# Mod 26

### Objective:

Cryptography can be easy, do you know what ROT13 is? 
cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}

### Commands / Steps:

```bash
# Step 1: Decode the line using the method to decode ROT13
echo "cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
# Alternative: 
# echo "cvpbPGS{arkg_gvzr_V'yy_gel_2_ebhaqf_bs_ebg13_GYpXOHqX}" | perl -pe 'y/A-Za-z/N-ZA-Mn-za-m/'
```

### Flag:

> picoCTF{next_time_I'll_try_2_rounds_of_rot13_TLcKBUdK}

### Notes / Tips

- `|` --> Sends the output of the first command as an input to the next command.
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'` --> Performs a letter substitution, mapping each letter to its ROT13 equivalent.


