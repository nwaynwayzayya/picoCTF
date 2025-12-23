# Client-side-again

### Description:

Can you break into this super secure portal?
Additional details will be available after launching your challenge instance.
`Click "Launch Instance".`
Can you break into this super secure portal?
http://fickle-tempest.picoctf.net:50489
Hint: What is obfuscation?

### Commands / Steps:

```bash
# Step 1: Go to the website and look at the source code using dev tools. 

# Step 2: There's a script in the html file but it looks like it's obfuscated(like the hint said). So, turn on pretty print(the curly brackets in the bottom corner of the screen).
<script type="text/javascript">
            var _0x5a46 = ['daf93}', '_again_4', 'this', 'Password\x20Verified', 'Incorrect\x20password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this'];
            (function(_0x4bd822, _0x2bd6f7) {
                var _0xb4bdb3 = function(_0x1d68f6) {
                    while (--_0x1d68f6) {
                        _0x4bd822['push'](_0x4bd822['shift']());
                    }
                };
                _0xb4bdb3(++_0x2bd6f7);
            }(_0x5a46, 0x1b3));
            var _0x4b5b = function(_0x2d8f05, _0x4b81bb) {
                _0x2d8f05 = _0x2d8f05 - 0x0;
                var _0x4d74cb = _0x5a46[_0x2d8f05];
                return _0x4d74cb;
            };
            function verify() {
                checkpass = document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];
                split = 0x4;
                if (checkpass[_0x4b5b('0x2')](0x0, split * 0x2) == _0x4b5b('0x3')) {
                    if (checkpass[_0x4b5b('0x2')](0x7, 0x9) == '{n') {
                        if (checkpass[_0x4b5b('0x2')](split * 0x2, split * 0x2 * 0x2) == _0x4b5b('0x4')) {
                            if (checkpass[_0x4b5b('0x2')](0x3, 0x6) == 'oCT') {
                                if (checkpass[_0x4b5b('0x2')](split * 0x3 * 0x2, split * 0x4 * 0x2) == _0x4b5b('0x5')) {
                                    if (checkpass['substring'](0x6, 0xb) == 'F{not') {
                                        if (checkpass[_0x4b5b('0x2')](split * 0x2 * 0x2, split * 0x3 * 0x2) == _0x4b5b('0x6')) {
                                            if (checkpass[_0x4b5b('0x2')](0xc, 0x10) == _0x4b5b('0x7')) {
                                                alert(_0x4b5b('0x8'));
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                } else {
                    alert(_0x4b5b('0x9'));
                }
            }
        </script>

# Step 3: After doing a lot of picoCTF challenges, the flag already looks obvious because there's always a pattern to the flags. 
var _0x5a46 = ['daf93}', '_again_4', 'this', 'Password\x20Verified', 'Incorrect\x20password', 'getElementById', 'value', 'substring', 'picoCTF{', 'not_this'];
# We will get the parts of the flag if we remove some irrelevant strings - 'Password\x20Verified', 'Incorrect\x20password', 'getElementById', 'value', 'substring' - and rearrange them in the usual pattern. 
```

### Flag:

> picoCTF{not_this_again_4daf93}

### Notes / Tips

- Obfuscation: Technique to make code harder to read/understand while maintaining functionality
- Client-Side Security: Never store sensitive logic or validation in client-side code
- Browser Tools: Use Developer Tools → Sources → Pretty Print for minified JavaScript

