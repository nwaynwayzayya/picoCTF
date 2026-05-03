# Some Assembly Required 1

### Description:
"Click `Launch Instance`." <br>
http://wily-courier.picoctf.net:51512/index.html

Hint: Try inspecting the WebAssembly module output and the loading script.

### Commands / Steps:

```bash
# Step 1: Go to the website. There's nothing to look around except for one input box to submit the flag, which we don't know yet.

# Step 2: Open Developer Tools and inspect the page sources. A suspicious JavaScript file, `G82XCw5CX3.js`, contains the loader logic.

# Step 3: Read `G82XCw5CX3.js`. The code is obfuscated, but it shows how the page loads and interacts with the WebAssembly module.

# Step 4: I tried to clean up the code by resolving the confusing function calls ('_0x') and renamed the variables. I put the cleaned up code under the source code below. 

# Step 5: In the clean up code, I realised that the password check is happening in the file below.
(async () => {
    // It fetches the WASM file: ./JIFxzHyW8W
    let response = await fetch('./JIFxzHyW8W');

# Step 6: So, we will download and read the file to see if the flag is in that file. 
wget http://wily-courier.picoctf.net:51512/JIFxzHyW8W
cat JIFxzHyW8W
# Output: The flag appears in the output near the bottom.
#                                A!A����!A����!  ����! ! !  G!A!  sA!             q!
 

# ?#����!A!  k!  6
#                    (
#                     ! !  :����

#                               2A�
#                                 +picoCTF{68ff4bc93f6d67637b2f471be209d132}
```

### Flag:

> picoCTF{68ff4bc93f6d67637b2f471be209d132}

### Notes / Tips

- This challenge hides the real logic in a WebAssembly binary loaded by an obfuscated JavaScript wrapper
- If the JavaScript looks unreadable, focus on the loading flow: fetch the WASM file, pass characters into it, then read the result
- The final flag may appear in the raw binary output or strings extracted from the WASM file


<br>

```bash
# Full Source Code
# Before editing some variables

const _0x402c = ['value', '2wfTpTR', 'instantiate', '275341bEPcme', 'innerHTML', '1195047NznhZg', '1qfevql', 'input', '1699808QuoWhA', 'Correct!', 'check_flag', 'Incorrect!', './JIFxzHyW8W', '23SMpAuA', '802698XOMSrr', 'charCodeAt', '474547vVoGDO', 'getElementById', 'instance', 'copy_char', '43591XxcWUl', '504454llVtzW', 'arrayBuffer', '2NIQmVj', 'result'];
const _0x4e0e = function(_0x553839, _0x53c021) {
    _0x553839 = _0x553839 - 0x1d6;
    let _0x402c6f = _0x402c[_0x553839];
    return _0x402c6f;
};
(function(_0x76dd13, _0x3dfcae) {
    const _0x371ac6 = _0x4e0e;
    while (!![]) {
        try {
            const _0x478583 = -parseInt(_0x371ac6(0x1eb)) + parseInt(_0x371ac6(0x1ed)) + -parseInt(_0x371ac6(0x1db)) * -parseInt(_0x371ac6(0x1d9)) + -parseInt(_0x371ac6(0x1e2)) * -parseInt(_0x371ac6(0x1e3)) + -parseInt(_0x371ac6(0x1de)) * parseInt(_0x371ac6(0x1e0)) + parseInt(_0x371ac6(0x1d8)) * parseInt(_0x371ac6(0x1ea)) + -parseInt(_0x371ac6(0x1e5));
            if (_0x478583 === _0x3dfcae)
                break;
            else
                _0x76dd13['push'](_0x76dd13['shift']());
        } catch (_0x41d31a) {
            _0x76dd13['push'](_0x76dd13['shift']());
        }
    }
}(_0x402c, 0x994c3));
let exports;
(async () => {
    const _0x48c3be = _0x4e0e;
    let _0x5f0229 = await fetch(_0x48c3be(0x1e9))
      , _0x1d99e9 = await WebAssembly[_0x48c3be(0x1df)](await _0x5f0229[_0x48c3be(0x1da)]())
      , _0x1f8628 = _0x1d99e9[_0x48c3be(0x1d6)];
    exports = _0x1f8628['exports'];
}
)();
function onButtonPress() {
    const _0xa80748 = _0x4e0e;
    let _0x3761f8 = document['getElementById'](_0xa80748(0x1e4))[_0xa80748(0x1dd)];
    for (let _0x16c626 = 0x0; _0x16c626 < _0x3761f8['length']; _0x16c626++) {
        exports[_0xa80748(0x1d7)](_0x3761f8[_0xa80748(0x1ec)](_0x16c626), _0x16c626);
    }
    exports['copy_char'](0x0, _0x3761f8['length']),
    exports[_0xa80748(0x1e7)]() == 0x1 ? document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)] = _0xa80748(0x1e6) : document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)] = _0xa80748(0x1e8);
}
```



```bash
# After cleaning up the code

let exports;

// This function loads the WebAssembly binary
(async () => {
    // It fetches the WASM file: ./JIFxzHyW8W
    let response = await fetch('./JIFxzHyW8W');
    
    // It converts the file to an array buffer and instantiates the WASM
    let wasmInstance = await WebAssembly.instantiate(await response.arrayBuffer());
    
    // It stores the WASM exported functions in the 'exports' variable
    exports = wasmInstance.instance.exports;
})();

function onButtonPress() {
    // 1. Get the value from the text box with id='input'
    let userInput = document.getElementById('input').value;

    // 2. Loop through your input and send each character to the WASM module
    for (let i = 0; i < userInput.length; i++) {
        // exports.copy_char(char_code, index)
        exports.copy_char(userInput.charCodeAt(i), i);
    }

    // 3. Add a null terminator to the end of the string in WASM memory
    exports.copy_char(0x0, userInput.length);

    // 4. Call the 'check_flag' function inside the WASM file
    // If it returns 1 (true), you got the flag!
    if (exports.check_flag() == 1) {
        document.getElementById('result').innerHTML = 'Correct!';
    } else {
        document.getElementById('result').innerHTML = 'Incorrect!';
    }
}
```