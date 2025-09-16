# what's a net cat?

### Objective:

Using netcat (nc) is going to be pretty important. Can you connect to jupiter.challenges.picoctf.org at port 41120 to get the flag?

### Commands / Steps:

```bash
# Step 1: Connect to the server using netcat
nc jupiter.challenges.picoctf.org 41120
```

### Flag:

> picoCTF{nEtCat_Mast3ry_3214be47}

### Notes / Tips

- `nc <host> <port>` --> Lets you read and write data across connections using TCP and UDP.