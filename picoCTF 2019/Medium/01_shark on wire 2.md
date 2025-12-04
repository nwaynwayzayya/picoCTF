# shark on wire 2

### Description:

We found this `packet capture`. Recover the flag.

### Commands / Steps:

***Step 1***: Download the pcap file.
`wget https://challenge-files.picoctf.net/c_fickle_tempest/edaf70675fae491d08043f5f626637436b05319785fa562e9274cdb4b09ec7ba/capture.pcap`

***Step 2***: Open the file with wireshark.

***Step 3***: There's no hint given so let's find anything suspicious. Let's first filter the packets by 'TCP' and check for anything suspicious.

***Step 4***: Next, we filter by 'UDP' and check for anything suspicious. 

***Step 5***: Everything looks fine until around the frame number 1104 where the destination port was different. It was port 22. And when we click the packet, in the packet data, we can see the word 'start'. It might be a clue as to where the flag starts.

***Step 6***: Then we filter the packets by 'udp and udp.dstport == 22' in the filter. 

***Step 7***: If we look at the source port number of the second packet, which is '5112', 112 is 'p' in ascii format. So it could be the start of the flag since the flags always start with 'pico'.

***Step 8***: Then we collect all the decimal values from all the packets. [ 112 105 99 111 67 84 70 123 112 49 76 76 102 51 114 51 100 95 100 97 116 97 95 118 49 97 95 115 116 51 103 48 125 ]

***Step 9***: We use an online decimal to ascii converter like cyberchef to convert the decimal values we got into a flag.


### Flag:

> picoCTF{p1LLf3r3d_data_v1a_st3g0}

### Notes / Tips

- Filtering: `udp.dstport == 22` filters packets sent to SSH port (unusual for UDP)
- ASCII Conversion: Decimal values → ASCII characters
- Wireshark Filters:
    - `udp` - Show UDP packets
    - `udp.dstport` == 22 - UDP packets to port 22
    - `udp.srcport` - Source port field contains data


