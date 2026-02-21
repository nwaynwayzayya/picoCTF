# waves over lambda

### Description:

We made a lot of substitutions to encrypt this. Can you decrypt it?
Additional details will be available after launching your challenge instance.
Click "Launch Instance".
Connect with nc fickle-tempest.picoctf.net 53349.

### Commands / Steps:

```bash
# Step 1: Connect with nc fickle-tempest.picoctf.net 53349.
# Output: 
-------------------------------------------------------------------------------
zcsnxmro ufxf io tckx qhmn - qxfykfszt_io_z_cdfx_hmjgwm_wmz18625
-------------------------------------------------------------------------------
af afxf scr jkzu jcxf rums m ykmxrfx cq ms uckx ckr cq ckx ouib rihh af oma ufx oisv, msw rufs i kswfxorccw qcx ruf qixor rijf aumr amo jfmsr gt m ouib qckswfxisn is ruf ofm.  i jkor mzvscahfwnf i umw umxwht ftfo rc hccv kb aufs ruf ofmjfs rchw jf ouf amo oisvisn; qcx qxcj ruf jcjfsr rumr ruft xmrufx bkr jf isrc ruf gcmr rums rumr i jinur gf omiw rc nc is, jt ufmxr amo, mo ir afxf, wfmw airuis jf, bmxrht airu qxinur, bmxrht airu ucxxcx cq jisw, msw ruf rucknuro cq aumr amo tfr gfqcxf jf.

# Step 2: We're not sure what kind of cipher this is so, first, let's try the magic recipe in cyberchef.
# Couldn't find any readable from the outputs.

# Step 3: Let's think it another way. The encoded paragraph has punctuations like comma, semi-colon, fullstops and spaces. So, this might be a Monoalphabetic Substitution. So let's try to decode the text in "dcode.fr" or "quipqiup.com" to see if we can decode it. 
# Result: It worked so, the first line is the flag.
congrats here is your flag - frequency_is_c_over_lambda_dac18625 ------------------------------------------------------------------------------- we were not much more than a quarter of an hour out of our ship till we saw her sink, and then i understood for the first time what was meant by a ship foundering in the sea. i must acknowledge i had hardly eyes to look up when the seamen told me she was sinking; for from the moment that they rather put me into the boat than that i might be said to go in, my heart was, as it were, dead within me, partly with fright, partly with horror of mind, and the thoughts of what was yet before me.
```

### Flag:

> frequency_is_c_over_lambda_dac18625

### Notes / Tips

- **Monoalphabetic substitution** replaces each letter with another letter consistently (A always becomes X, B always becomes Y, etc.)
- **Key indicators**: Punctuation and spaces are preserved, word structure remains intact
- **Automated solvers**: Use dcode.fr, quipqiup.com, or CyberChef's "Substitute" tool for quick decryption
- **Manual approach**: Look for single-letter words (I, A), common words (THE, AND), and letter frequency patterns 


