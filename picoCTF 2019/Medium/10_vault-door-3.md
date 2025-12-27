# vault-door-3

### Description:

This vault uses for-loops and byte arrays.
The source code for this vault is here: `VaultDoor3.java`
Hint: Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filelink]

# Step 2: View the file. 
cat VaultDoor3.java
# The password part is, like other VaultDoor challenges, in the checkPassword() function.
public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm11g54e_u_4_m4r042");
    }

# Step 3: Analyse the checkPassword() function.
# The password is scrambled through four different for-loops.
# We need to reverse the scrambling to find the original password.

# Step 4: We will write the python code to reverse this. 
def find_password():
    target = list("jU5t_a_sna_3lpm11g54e_u_4_m4r042")
    password = ['?'] * 32
    
    # Map from password index to target index
    # We know: target[i] = password[some_index]
    
    # Rule 1: buffer[i] = password[i] for i=0-7
    # So: target[0-7] = password[0-7]
    for i in range(8):
        password[i] = target[i]
    
    # Rule 2: buffer[i] = password[23-i] for i=8-15
    # So: target[8-15] = password[23-i]
    # Therefore: password[23-i] = target[i] for i=8-15
    for i in range(8, 16):
        password[23 - i] = target[i]
    
    # Rule 3: buffer[i] = password[46-i] for i=16,18,20,...,30
    # So: target[i] = password[46-i] for i in [16,18,20,22,24,26,28,30]
    for i in range(16, 32, 2):
        password[46 - i] = target[i]
    
    # Rule 4: buffer[i] = password[i] for i=31,29,27,...,17
    # So: target[i] = password[i] for i in [31,29,27,25,23,21,19,17]
    for i in range(31, 16, -2):
        password[i] = target[i]
    
    return ''.join(password)

print("Password:", find_password())
```

### Flag:

> picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_e45012}

### Notes / Tips

- Reverse Engineering: Need to trace the scrambling process backwards to recover original input
- Four Transformation Rules:
    - First 8 characters copied directly
    - Next 8 characters reversed with offset (23-i)
    - Even indices (16-30) mapped with formula (46-i)
    - Odd indices (17-31) copied directly


