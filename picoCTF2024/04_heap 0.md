# heap 0 

### Description:

Are overflows just a stack concern?
Download the binary `here`.
Download the source `here`.
Additional details will be available after launching your challenge instance.

Connect with the challenge instance here:
`nc tethys.picoctf.net 53606`

### Commands / Steps:

```bash
# Note: The program allocates two heap buffers back-to-back: input_data and safe_var.
# It uses an unsafe input function (e.g. scanf("%s", input_data) or similar) with no bounds check when writing into input_data.
# Because the write is unbounded, you can write past the end of input_data and overwrite adjacent heap memory — in particular, safe_var.
# The program later checks safe_var. If the value differs from the original expected value, it prints the flag. So the exploit is simply to overwrite safe_var.

# Step 1: # Step 1: Connect to remote using nc.
nc tethys.picoctf.net 53606
# Output: 
# Welcome to heap0!
# I put my data on the heap so it should be safe from any tampering.
# Since my data isn't on the stack I'll even let you write whatever info you want to the heap, I already took care of using malloc for you.

# Heap State:
# +-------------+----------------+
# [*] Address   ->   Heap Data   
# +-------------+----------------+
# [*]   0x56a9a6d492b0  ->   pico
# +-------------+----------------+
# [*]   0x56a9a6d492d0  ->   bico
# +-------------+----------------+

# 1. Print Heap:          (print the current state of the heap)
# 2. Write to buffer:     (write to your own personal block of data on the heap)
# 3. Print safe_var:      (I'll even let you look at my variable on the heap, I'm confident it can't be modified)
# 4. Print Flag:          (Try to print the flag, good luck)
# 5. Exit

# Step 2: Choose option 2 and send a long string to overwrite safe_var.

# Step 3: Choose option 4 and we will get the flag.
```

### Flag:

> picoCTF{my_first_heap_overflow_1ad0e1a6}

### Notes / Tips

- Overflow one heap buffer to overwrite an adjacent heap value; changing any byte in the target makes the check fail and prints the flag.


