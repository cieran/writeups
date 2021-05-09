## cookin the ramen (50 Points)

### Problem
```
Apparently we made cookin the books too hard, here's some ramen to boil as a warmup:

.--- ...- ...- . ....- ...- ... ..--- .. .-. .-- --. -.-. .-- -.- -.-- -. -... ..--- ..-. -.-. ...- ...-- ..- --. .--- ... ..- .. --.. -.-. .... -- ...- -.- . ..- -- - . -. ...- -. ..-. --- -.-- --.. - .-.. .--- --.. --. --. ...-- ... -.-. -.- ..... .--- ..- --- -. -.- -..- -.- --.. -.- ...- ..- .-- - -.. .--- -... .... ..-. --. --.. -.- -..- .. --.. .-- ...- ... -- ...-- --.- --. ..-. ... .-- --- .--. .--- .....
```

### Solution
Okay, very obviously we have morse code to decode. Running through an online decoder we get:

`JVVE4VS2IRWGCWKYNB2FCV3UGJSUIZCHMVKEUMTENVNFOYZTLJZGG3SCK5JUONKXKZKVUWTDJBHFGZKXIZWVSM3QGFSWOPJ5`

and then giving a quick run through our good friend Magic by CyberChef, we get our flag.

It looks like the algorithm for this challenge was:

Plaintext -> Base58 -> Base64 -> Base32 -> Morse -> Ciphertext



Flag: `DawgCTF{0k@y_r3al_b@by's_f1r5t}`
