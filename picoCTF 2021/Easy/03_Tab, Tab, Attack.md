# Tab, Tab, Attack

### Objective:

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip

### Commands / Steps:

```bash
# Step 1: First, we download the zip file.
wget https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip

# Step 2: Unzip the file.
unzip Addadshashanammu.zip
# Output
# Archive:  Addadshashanammu.zip
#    creating: Addadshashanammu/
#    creating: Addadshashanammu/Almurbalarammi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
#   inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet

# Step 3: Go into the deepest directory where the file exists. 
 cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/

# Step 4: Execute the file
./fang-of-haynekhtnamet
# *ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}
```

### Flag:

> picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}

### Notes / Tips

- Use tab completion to navigate deep directory structures quickly.
- unzip [file.zip] → extract contents of a zip file.
- cd [directory] → change into a directory.



