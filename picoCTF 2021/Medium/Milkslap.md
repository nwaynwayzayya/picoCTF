# Milkslap

### Description:
🥛
Additional details will be available after launching your challenge instance.
"Click `Launch Instance`." <br>
http://wily-courier.picoctf.net:51846/

Hint: Look at the problem category (Forensics)

### Commands / Steps:

```bash
# Step 1: Open the site from the challenge.

# Step 2: There's only a live picture that moves when we moves our mouse over it.

# Step 3: Check the source code of the page using developer tools.

# Step 4: index.html and script.js didn't help, but style.css pointed to `concat_v.png`, so that looked worth checking.
wget http://wily-courier.picoctf.net:51846/concat_v.png

# Step 5: I tried a few image tools and `zsteg` ended up being the one that worked.
# If you need it, install it with: sudo gem install zsteg.
zsteg concat_v.png

# Output:
# /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
#         from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
#          ... 10225 levels...
#         from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
#         from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
#         from /usr/local/bin/zsteg:25:in `load'
#         from /usr/local/bin/zsteg:25:in `<main>'

# Step 6: `zsteg` crashed the first time, so I bumped Ruby's stack size and ran it again.
export RUBY_THREAD_VM_STACK_SIZE=500000000
# Then run the 'zsteg' command again.
zsteg concat_v.png
# imagedata           .. text: "\n\n\n\n\n\n\t\t"
# chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 1280 colors; 1st RGB space (0), w 0xb9a0, x 0x802, y 0, z 0; 2nd HSB space (1), w 0, x 0, y 0, z 0                                                                                                      
# b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
# b1,bgr,lsb,xy       .. <wbStego size=0x941a5b ext=nil data="\xB6\xAD\xB6}\xDB\xB2lR\x7F\xDF\x86\xB7c\xFC\xFF\xBF\x02Zr\x8E\xE2Z\x12\xD8q\xE5&MJ-X:\xB5\xBF\xF7\x7F\xDB\xDFI\bm\xDB\xDB\x80m\x00\x00\x00\xB6m\xDB\xDB\xB6\x00\x00\x00\xB6\xB6\x00m\xDB\x12\x12m\xDB\xDB\x00\x00\x00\x00\x00\xB6m\xDB\x00\xB6\x00\x00\x00\xDB\xB6mm\xDB\xB6\xB6\x00\x00\x00\x00\x00m\xDB" even=true hdr=nil enc=nil mix=true controlbyte="[">                                                                                                                                 
# b2,r,lsb,xy         .. text: ["U" repeated 8 times]
# b2,r,msb,xy         .. file: VISX image file
# b2,g,lsb,xy         .. file: VISX image file
# b2,g,msb,xy         .. file: SoftQuad DESC or font file binary - version 15722
# b2,b,msb,xy         .. text: "UfUUUU@UUU"
# b4,r,lsb,xy         .. text: "\"\"\"\"\"#4D"
# b4,r,msb,xy         .. text: "wwww3333"
# b4,g,lsb,xy         .. text: "wewwwwvUS"
# b4,g,msb,xy         .. text: "\"\"\"\"DDDD"
# b4,b,lsb,xy         .. text: "vdUeVwweDFw"
# b4,b,msb,xy         .. text: "UUYYUUUUUUUU"
```

### Flag:

> picoCTF{imag3_m4n1pul4t10n_sl4p5}

### Notes / Tips

- This is a forensics challenge: the flag is hidden inside an image rather than in the page itself
- Check page source and linked assets, because clues often live in CSS/JS references instead of HTML content
- `zsteg` is useful for PNG steganography, especially when metadata and source files do not reveal the answer
- If `zsteg` crashes on a large file, increasing `RUBY_THREAD_VM_STACK_SIZE` can help it finish decoding


