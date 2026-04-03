# la cifra de

### Description:
I found this cipher in an old book.
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
Can you figure out what it says? Connect with `nc fickle-tempest.picoctf.net 63605`.

Hint: There are tools that make this easy. / Perhaps looking at history will help

### Commands / Steps:

```bash
# Step 1: Connect to the instance.
nc fickle-tempest.picoctf.net 63605
# Encrypted message:
# Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

# Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

# Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo 

# Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3x149hNchj}

# Ehk ktryy herq-ooizxetypd jjdcxnatoty ol f aordllvmlbkytc inahkw socjgex, bls sfoe gwzuti 1467 my Rjzn Hfetoxea Gqmexyt.

# Tnj Gimjyèrk Htpnjc iy ysexjqoxj dosjeisjd cgqwej yse Gqmexyt Doxn ox Fwbkwei Inahkw.

# Tn 1508, Ptsatsps Zwttnjxiax tnbjytki ehk xz-cgqwej ylbaql rkhea (g rltxni ol xsilypd gqahggpty) ysaz bzuri wazjc bk f nroytcgq nosuznkse ol yse Bnretèwp Cousex.

# Gplrfdo’y xpcuso butvlky lpvjlrki tn 1555 gx l cuseitzltoty ol yse lncsz. Yse rthex mllbjd ol yse gqahggpty fce tth snnqtki cemzwaxqj, bay ehk fwpnfmezx lnj yse osoed qptzjcs gwp mocpd hd xegsd ol f xnkrznoh vee usrgxp, wnnnh ify bk itfljcety hizm paim noxwpsvtydkse.

# Step 2: So, I tried to find some famous old ciphers on google first. I found Caesar Cipher, Scytale Cipher, Vigenère Cipher (also called "le chiffre indéchiffrable"), Pigpen/Freemason Cipher, and many more. 

# Step 3: From there, I noticed something interesting. The other name for "Vigenère Cipher" sounds a bit same to the challenge's name. So, I thought there'd be some connections there.

# Step 4: There's a great website where we can identify the type of cipher by inputting the cipher into it, called (https://www.dcode.fr/cipher-identifier). In that website, I tried to check the cipher type and I got "Vigenère Cipher" on the top. 

# Step 5: Then, we'll try decrypting the cipher. We can use both https://www.dcode.fr/vigenere-cipher and Cyberchef. For now, I'll use the dcode.fr website.

# Step 6: There are several decryption methods available to us. I'll try to use the method, "Knowing a plaintext word:" first. Since the flag usually contains "picoctf". I tried that. Didn't work.

# Step 7: Then I tried the "Knowing the Key/Password:" method, using the key words like pico, picoctf, ctf, flag, etc. It worked with the keyword "flag". Only the half was decrypted in the website "dcode.fr" unfortunately. 

# Step 8: I moved to cyberchef website and decrypted the whole message again using the keyword "flag". There's our flag.
```

### Flag:

> picoCTF{b311a50_0r_v1gn3r3_c1ph3r149cCcbe}

### Notes / Tips

- "La cifra indéchiffrable" is another name for the Vigenère cipher
- The title and hint both point to a historical polyalphabetic cipher
- Use cipher identifier tools first if the encryption type is unclear

