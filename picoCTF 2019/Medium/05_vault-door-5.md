# vault-door-5

### Description:

In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding!
The source code for this vault is here: `VaultDoor5.java`

### Commands / Steps:

```bash
# Step 1: Download the file.
wget https://challenge-files.picoctf.net/c_fickle_tempest/bd4f8f70a70dacc0e57dfc24ff34f5297a3db3c9c4366fd8df02f6bf47c794c8/VaultDoor5.java

# Step 2: We checked the file contents. We can see from both the main function and then the check password function on how to get our flag. The source code below the notes section.
public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTYyJTY1JTM5JTY2JTMxJTMwJTYxJTM0";
        return base64Encoded.equals(expected);
    }

# Step 3: We can go to Cyberchef and use two operations, URL Decode and From Base64, into the recipe and get the password.

# Step 4: We compile and then run the java program.
javac VaultDoor5.java   # We get the executable java program afterwards.
java VaultDoor5

# Step 5: We are prompted to enter the password. It's in picoCTF flag format according to the main function in the java source code.
Enter vault password: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_be9f10a4}
Access granted.
```

### Flag:

> picoCTF{c0nv3rt1ng_fr0m_ba5e_64_be9f10a4}

### Notes / Tips

- Encoding Chain: `Password → URL Encode (%XX) → Base64 Encode`
- Solve Method: `Reverse the process: Base64 Decode → URL Decode`
- CyberChef Recipe:
    - Input: The long expected string
    - Operations: "From Base64" → "URL Decode"
    - Output: c0nv3rt1ng_fr0m_ba5e_64_be9f10a4
- Flag Format: Wrap in picoCTF{}
- Key Insight: Multiple encodings ≠ encryption. Always decode in reverse order!


```bash

import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);   #!!!!The password format we will need to enter after we run the program.
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    # // Minion #7781 used base 8 and base 16, but this is base 64, which is
    # // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    # // brother Minion #2415 says, anyway.
    # //
    # // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    # The encoded password format.
    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTYyJTY1JTM5JTY2JTMxJTMwJTYxJTM0";
        return base64Encoded.equals(expected);
    }

```


