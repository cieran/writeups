## BBomb Phase 3 (75 Points)

### Problem
```
Reflections? Rotations? Translations? This is starting to sound like geometry...

"_9~Jb0!=A`G!06qfc8'_20uf6`2%7
```

### Solution
This challenge was a case of trial and error for me. I went through multiple different cipher decoders on DCode to try see if the plaintext would fall out.
After trying ROT47, the output was:
`Q0hOy3_Plp1vP_eB74gV0a_F7e1aTf`

I was suspicious because of the format and began to suspect there could be multiple ciphers at play here. Given the placement of the underscores, I thought of alphabetic shift ciphers. I tried bruteforcing this on DCode's Shift Cipher tool and after 13 rotations, out fell the plaintext.

`D0uBl3_Cyc1iC_rO74tI0n_S7r1nGs`


Flag: `DawgCTF{D0uBl3_Cyc1iC_rO74tI0n_S7r1nGs}`
