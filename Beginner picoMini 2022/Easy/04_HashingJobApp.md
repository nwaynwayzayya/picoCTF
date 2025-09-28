# HashingJobApp

### Description:

If you want to hash with the best, beat this test!
`nc saturn.picoctf.net 62163`

### Commands / Steps:

```bash
# Step 1: Connect to the host with netcat. 
nc saturn.picoctf.net 62163
#Output: Please md5 hash the text between quotes, excluding the quotes: 'Japan'
#Answer: 

# Step 2: We can use md5 online hasher or command line to hash. It will prompt you to hash three different texts and you will get the flag after that.
```

### Flag:

> picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}

### Notes / Tips

- `echo -n "Japan" | md5sum` --> Hash text into md5
    - `-n` prevents echo from adding a newline character, which would otherwise change the hash result.

