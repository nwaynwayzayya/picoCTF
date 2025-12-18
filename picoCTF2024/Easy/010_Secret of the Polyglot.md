# Secret of the Polyglot

### Description:

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file `here`.

### Commands / Steps:

```bash
# Step 1: Download the file.
wget <filelink>

# Step 2: Open the file and we can see that there's the second part of flag in it.

# Step 3: Check the file type.
file flag2of2-final.pdf
# Output:
# flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced
# Output shows that it's actually a png file.

# Step 4: We will try chaning the extension of the file from pdf to png.
mv flag2of2-final.pdf flag2of2-final.png

# Step 5: Now that it's a png image, we can try opening it to see if there's the first part of the flag.
# Note: There's the first part of the flag in the image.
```

### Flag:

> picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}

### Notes / Tips

- File extensions can be misleading; always check the actual file type using the `file` command.

- `“Polyglot”` files contain multiple valid formats in one file; in this case, a `PNG` image was disguised with a `.pdf` extension.


