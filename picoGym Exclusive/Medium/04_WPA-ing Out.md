# WPA-ing Out

### Description:

I thought that my password was super-secret, but it turns out that passwords passed over the AIR can be CRACKED, especially if I used the same wireless network password as one in the rockyou.txt credential dump.
Use this '`pcap file`' and the rockyou wordlist. The flag should be entered in the picoCTF{XXXXXX} format.

### Commands / Steps:

```bash
# Step 1: Download the pcap file.
wget https://artifacts.picoctf.net/c/41/wpa-ing_out.pcap

# Step 2: Download the 'rockyou.txt'. 
wget https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt -O rockyou.txt

# Step 3: Crack the password using aircrack-ng and rockyou.txt.
aircrack-ng -w rockyou.txt wap-ing.pcap
# We get the password and then we can submit the flag in picoCTF flag format.
```

### Flag:

> picoCTF{mickeymouse}

### Notes / Tips

- `aircrack-ng` - Tool for cracking WPA/WPA2 wireless passwords
- `-w rockyou.txt` - Specifies the wordlist to use for cracking
- `WPA Handshake`: The pcap file contains a captured WPA handshake that can be cracked offline
- `rockyou.txt`: Common password wordlist containing millions of real passwords




