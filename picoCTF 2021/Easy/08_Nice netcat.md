# Nice Netcat...

### Objective:

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...

### Commands / Steps:

```bash
# Step 1: We connect to the server using netcat.
nc mercury.picoctf.net 35652
# Output: A long list of numbers.

# Step 2: We use python to convert those numbers into ASCII.
nc mercury.picoctf.net 35652 | python3 -c "import sys;print(''.join(chr(int(i)) for i in sys.stdin.read().split()))"
```

### Flag:

> picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}

### Notes / Tips

- `nc <host> <port>` --> Lets you read and write data across connections using TCP and UDP.
- Python one-liner explained:
    - `python3 -c` → Runs Python code from the command line.
    - `sys.stdin.read().split()` → Reads all numbers from input and splits them into a list.
    - `int(i)` → Converts each string number into an integer.
    - `chr(int(i))` → Converts the integer to its ASCII character.
    - `''.join(...)` → Joins all characters into the flag string.