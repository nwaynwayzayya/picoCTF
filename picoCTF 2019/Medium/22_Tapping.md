# Tapping

### Description:

Theres tapping coming in from the wires.
Additional details will be available after launching your challenge instance.
Click "Launch Instance".
Hint: What kind of encoding uses dashes and dots?

### Commands / Steps:

```bash
# Step 1: Connect to the instance.
nc fickle-tempest.picoctf.net 57186
# Output: 
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .- -.. . ----- ----- ----- ----. .---- }

# Step 2: It's clearly "Morse Code". So we can find an online translator and translate it directly(we need to exclude the "{}" of course). Then, we'll get the flag.
```

### Flag:

> PICOCTF{M0RS3C0D31SFUNADE00091}

### Notes / Tips

- **Morse code**: Uses dots (.) and dashes (-) to represent letters and numbers
- **Recognition**: "Dashes and dots" encoding hint + "tapping" title = Morse code
- **Online tools**: Search "morse code decoder" or use CyberChef's "From Morse Code" recipe
- **Common patterns**: SOS = `... --- ...`, E = `.` (most common letter), T = `-` 


