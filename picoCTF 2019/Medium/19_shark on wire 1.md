# shark on wire 1

### Description:

We found this `packet capture`. Recover the flag.
Hint: Try using a tool like Wireshark, What are streams?

### Commands / Steps:

```bash
# Step 1: Download the file.

# Step 2: Normally, in ctf challenges, we find the flags in tcp or udp streams. (The Hint also tells us about streams.)

# Step 3: Let's filter the TCP streams first. There are only a few packets. I tried following the streams of those, but found nothing.

# Step 4: Now, we filter by UDP. I entered the filter ' udp contains "pico" '. I found four malformed packets including the string 'pico'.
# Packet numbers - 55, 57, 59, 61

# Step 5: Let's check the UDP packets after those packet numbers. The first UDP packet after those, packet number 63, has the letter 'p' in them. So, I followed the UDP stream of that packet and got the flag.
```

### Flag:

> picoCTF{StaT31355_636f6e6e}

### Notes / Tips

- **Wireshark filters**: Use `udp contains "pico"` or `tcp contains "flag"` to quickly find relevant packets
- **Follow streams**: Right-click packet → "Follow" → "TCP/UDP Stream" to see full conversation data
- **Check malformed packets**: Often contain hidden data or clues in CTF challenges
- **Common locations**: Flags typically hidden in TCP/UDP streams, packet payloads, or HTTP data 


