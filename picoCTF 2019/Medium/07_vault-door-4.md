# vault-door-4

### Description:

This vault uses ASCII encoding for the password.
The source code for this vault is here: `VaultDoor4.java`
Hint: Use a search engine to find an "ASCII table" / You will also need to know the difference between octal, decimal, and hexadecimal numbers.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filename]

# Step 2: View the script.
cat VaultDoor4.java

# Step 3: We can decode the password outselves manually. The password clue is in the 'checkPassword()' function.
public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,   # Decimal
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,   # Hexadecimal
            0142, 0131, 0164, 063 , 0163, 0137, 066 , 064 ,   # Octal
            'e' , '1' , '3' , 'd' , '0' , '0' , 'b' , '2' ,   # Chatacter literals
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
# We will get the flag after decoding them with the ASCII tables online.
```

### Flag:

> picoCTF{jU5t_4_bUnCh_0f_bYt3s_64e13d00b2}

### Notes / Tips

- Number Systems: The challenge tests understanding of different number representations:
    - Decimal: Base 10 (e.g., 106, 85, 53)
    - Hexadecimal: Base 16, prefixed with 0x (e.g., 0x55 = 85 decimal)
    - Octal: Base 8, prefixed with 0 (e.g., 0142 = 98 decimal)
    - Character Literals: Direct ASCII characters (e.g., 'e' = 101 decimal)


