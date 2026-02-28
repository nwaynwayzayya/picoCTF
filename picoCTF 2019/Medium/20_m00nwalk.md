# m00nwalk

### Description:
Decode this `message` from the moon.
Hint: How did pictures from the moon landing get sent back to Earth? / What is the CMU mascot?, that might help select a RX option

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filename]

# Step 2: It's an audio file, so I tried opening it first. Everything is just strange and unusual sounds. Then I checked the file type and exiftool first to see if the flag is hidden in there. 
file message.wav
# message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz
exiftool message.wav
# ExifTool Version Number         : 13.25
# File Name                       : message.wav
# Directory                       : .
# File Size                       : 11 MB
# File Modification Date/Time     : 2025:11:21 13:10:37-06:00
# File Access Date/Time           : 2026:02:28 11:37:10-06:00
# File Inode Change Date/Time     : 2026:02:28 11:37:02-06:00
# File Permissions                : -rw-rw-r--
# File Type                       : WAV
# File Type Extension             : wav
# MIME Type                       : audio/x-wav
# Encoding                        : Microsoft PCM
# Num Channels                    : 1
# Sample Rate                     : 48000
# Avg Bytes Per Sec               : 96000
# Bits Per Sample                 : 16
# Duration                        : 0:01:55

# Step 3: Let's try to google what the hint says about the technique to send the pictures back to the earth from the moon. 
# It's by a specialized Slow-Scan Television (SSTV) system. 

# Step 4: I tried to find online how to convert from SSTV into a png file. Fortunately, there are browser-based sstv decoder, so I just uploaded the message.wav into it, and it gave me an image with the flag in it.
```

### Flag:

> picoCTF{beep_boop_im_in_space}

### Notes / Tips

- **SSTV (Slow-Scan Television)**: Used by NASA to send images from moon missions back to Earth
- **Audio steganography**: Images can be encoded as audio signals that sound like strange beeps/static
- **Online tools**: Search "SSTV decoder online" or "wav to image converter" for browser-based solutions
- **Desktop tools**: QSSTV (Linux), MMSSTV (Windows), or RX-SSTV for more advanced decoding options


