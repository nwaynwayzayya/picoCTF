# Mr-Worldwide

### Description:

A musician left us a `message`. What's it mean?

### Commands / Steps:

```bash
# Step 1: Download the file.
wget [filelink]

# Step 2: View the contents of the file to see what's inside.
cat message.txt
# picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}

# Step 3: I don't know what these are so I try to google the first pair first, 5.028309, 135.753082. Then, I realised they are  Decimal Degree GPS coordinates for Latitude and Longitude. 
"""
35.028309, 135.753082  --> Kyoto, Japan
46.469391, 30.740883 --> Odesa Oblast, Ukraine
39.758949, -84.191605 --> Dayton, Ohio, USA
41.015137, 28.979530 --> İstanbul, Türkiye
24.466667, 54.366669 --> Abu Dhabi - United Arab Emirates
3.140853, 101.693207 --> Kuala Lumpur, Federal Territory of Kuala Lumpur, Malaysia
_
9.005401, 38.763611 --> Addis Ababa, Ethiopia
-3.989038, -79.203560 --> Loja, Ecuador
52.377956, 4.897070 --> Amsterdam, Netherlands
41.085651, -73.858467 --> Sleepy Hollow, New York, USA
57.790001, -152.407227 --> Kodiak, Alaska, USA
31.205753, 29.924526 --> Alexandria, Egypt
"""

# Step 4: Take the first letter of each city name to spell out the flag.
K-yoto + O-desa + D-ayton + I-stanbul + A-bu Dhabi + K-uala Lumpur + _ + A-ddis Ababa + L-oja + A-msterdam + S-leepy Hollow + K-odiak + A-lexandria = KODIAK_ALASKA
```

### Flag:

> picoCTF{KODIAK_ALASKA}

### Notes / Tips

- **GPS coordinates** are in decimal degree format: (latitude, longitude) 
- Use Google Maps or coordinate lookup tools to convert coordinates to city names
- Look for patterns when you have multiple data points - first letters, last letters, etc. 


