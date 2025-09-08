# Enhance!

### Objective:

Download this image file and find the flag.
`Download image file`

### Commands / Steps:

```bash
# Step 1: Download the image file. 
wget https://artifacts.picoctf.net/c/101/drawing.flag.svg

# Step 2: We check the source code of the image.
cat drawing.flag.svg
# If we look at the source code, we can notice that there are letters inside the 'tspan' tags.
# The <tspan> tags in the SVG define text chunks in the drawing. Since the flag is hidden there, we can extract them using grep "tspan".

# Step 3: Use grep to extract the flags.
cat drawing.flag.svg | grep "tspan"
# Output:
# id="text3723"><tspan
#     id="tspan3748">p </tspan><tspan
#     id="tspan3754">i </tspan><tspan
#     id="tspan3756">c </tspan><tspan
#     id="tspan3758">o </tspan><tspan
#     id="tspan3760">C </tspan><tspan
#     id="tspan3762">T </tspan><tspan
#     id="tspan3764">F { 3 n h 4 n </tspan><tspan
#     id="tspan3752">c 3 d _ 2 4 3 7 4 6 7 5 }</tspan></text>
```

### Flag:

> picoCTF{3nh4nc3d_24374675}

### Notes / Tips

- SVG files are XML-based, so flags can be hidden inside tags like `<tspan>`.
- Always check the source code of files (images, audio, etc.) in CTFs — the flag is often hidden in metadata or tag content.

