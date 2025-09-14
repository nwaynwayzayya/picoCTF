# dont-use-client-side

### Objective:

Can you break into this super secure portal? https://jupiter.challenges.picoctf.org/problem/17682/ (`link`) or http://jupiter.challenges.picoctf.org:17682

### Commands / Steps:

```bash
# Step 1: We visit the link in our browser.

# Step 2: We are taken to a site where we need to type our password in.

# Step 3: This is a web exploitation challenge so first, we inspect the page by right clicking on it and clicking inspect afterwards.

# Step 4: We check the element tab first and find the password.
function verify() {
   checkpass = document.getElementById("pass").value;
   split = 4;
   if (checkpass.substring(0, split) == 'pico') {
     if (checkpass.substring(split*6, split*7) == '706c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_b') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '5}') {
                  alert("Password Verified")
                  }
                }
              }
        
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }

# Step 4: We can get the flag if we order the substrings.
```

### Flag:

> picoCTF{no_clients_plz_b706c5}

### Notes / Tips

- In challenges like this, always check:
    - HTML source (View Page Source)
    - Inline scripts
    - External .js files


