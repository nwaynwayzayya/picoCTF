# Flag in Flame

### Description:

The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log.
Download the encoded data `here`: Logs Data. Be prepared—the file is large, and examining it thoroughly is crucial .

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://challenge-files.picoctf.net/c_amiable_citadel/5da19ac1eabba5f0b9287e4a5675612e5bbffc68aaa8fa54c58ebd5ce81e29fd/logs.txt

# Step 2: Since it is said that the file is long, let's check the last line of the file.
cat logs.txt | tail -n 1

# Step 3: The last line ends in "......HUXk/wPPovWATfmXnAAAAABJRU5ErkJggg==". This is base64 encoded.
cat logs.txt | base64 -d > decodedlogs.txt

# Step 4: Check the file type of the decodedlogs.txt file.
file decodedlogs.txt
# decodedlogs.txt: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced

# Step 5: It's png image data so let's change the file extension. 
mv decodedlogs.txt decodedlogs.png

# Step 6: If we open and view the image, we can see the hex string in the picture. (7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E6E675F62396163346362397D)

# Step 7: Let's decode the hex string to get the flag. 
echo 7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F62396163346362397D | xxd -r -p

```

### Flag:

> picoCTF{forensics_analysis_is_amazing_b9ac4cb9}

### Notes / Tips

- `tail -n 1` - View last line of large files (efficient for big files)
- `base64 -d` - Decode base64 content (recognizable by = padding at end)
- `file` - Identify file type from magic bytes/headers
- `xxd -r -p` - Convert hex to ASCII (-r = reverse, -p = plain hex)
- File Extension Correction: Always rename files after identifying their true type
- Base64 Indicators: Strings ending with = or == are likely base64



