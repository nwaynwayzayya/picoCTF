# Log Hunt

### Description:

Our server seems to be leaking pieces of a secret flag in its logs. The parts are scattered and sometimes repeated. Can you reconstruct the original flag?
Download the `logs` and figure out the full flag from the fragments.

### Commands / Steps:

```bash
# Step 1: Download the log file.
wget https://challenge-files.picoctf.net/c_amiable_citadel/49cec6157142f24a599f4164d5b63322c2494f801390d6f22eb91b3aa592bc66/server.log

# Step 2: View the file contents of the file.
cat server.log
# There were a lot of logs in the file.

# Step 3: Let's filter the output by using grep to find the flag.
cat server.log | grep pico
# Output: 
# [1990-08-09 10:00:10] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:04:27] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:04:29] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:04:37] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:19:23] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:19:29] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:19:32] INFO FLAGPART: picoCTF{us3_

# Step 4: Filter by the text "INFO FLAGPART" with grep.
cat server.log | grep INFO FLAGPART
# [1990-08-09 10:00:10] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 10:02:55] INFO FLAGPART: y0urlinux_
# [1990-08-09 10:05:54] INFO FLAGPART: sk1lls_
# [1990-08-09 10:05:55] INFO FLAGPART: sk1lls_
# [1990-08-09 10:10:54] INFO FLAGPART: cedfa5fb}
# [1990-08-09 10:10:58] INFO FLAGPART: cedfa5fb}
# [1990-08-09 10:11:06] INFO FLAGPART: cedfa5fb}
# [1990-08-09 11:04:27] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:04:29] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:04:37] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 11:09:16] INFO FLAGPART: y0urlinux_
# [1990-08-09 11:09:19] INFO FLAGPART: y0urlinux_
# [1990-08-09 11:12:40] INFO FLAGPART: sk1lls_
# [1990-08-09 11:12:45] INFO FLAGPART: sk1lls_
# [1990-08-09 11:16:58] INFO FLAGPART: cedfa5fb}
# [1990-08-09 11:16:59] INFO FLAGPART: cedfa5fb}
# [1990-08-09 11:17:00] INFO FLAGPART: cedfa5fb}
# [1990-08-09 12:19:23] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:19:29] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:19:32] INFO FLAGPART: picoCTF{us3_
# [1990-08-09 12:23:43] INFO FLAGPART: y0urlinux_
# [1990-08-09 12:23:45] INFO FLAGPART: y0urlinux_
# [1990-08-09 12:23:53] INFO FLAGPART: y0urlinux_
# [1990-08-09 12:25:32] INFO FLAGPART: sk1lls_
# [1990-08-09 12:28:45] INFO FLAGPART: cedfa5fb}
# [1990-08-09 12:28:49] INFO FLAGPART: cedfa5fb}
# [1990-08-09 12:28:52] INFO FLAGPART: cedfa5fb}
```

### Flag:

> picoCTF{us3_y0urlinux_sk1lls_cedfa5fb}

### Notes / Tips

- Alternative - Extract unique flag parts in chronological order
    - `grep "INFO FLAGPART" server.log | awk -F': ' '{print $2}' | sort -u`
- Tool Used: grep + awk + uniq - filter and process log data
- Pattern: Flag was split into parts scattered throughout the logs


