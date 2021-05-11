## These Ladies Paved Your Way (150 Points)

### Problem
```
Per womenintech.co.uk, these 10 women paved your way as technologists. One of them holds more than 100 issued patents and is known for writing understandable textbooks about network security protocols. What other secrets does she hold?

file: WomenInTech.zip
```

### Solution
We're given a quick overview on 10 women who are trailblazers in tech and a ZIP file containing 10 JPEGs on, 1 for each of these women. One in particular was mentioned in the problem spec and how she holds more than 100 patents. So I googled this, and found out it was Radia Perlman.
My next step was to run `exiftool` on Perlman's JPEG.

```
❯ exiftool radia_perlman.jpg
ExifTool Version Number         : 12.21
File Name                       : radia_perlman.jpg
Directory                       : .
File Size                       : 10 KiB
...
...
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 8d370a1f7871e76616c0f06987707b84
Credit                          : U3Bhbm5pbmdUcmVlVmlnCg==
Keywords                        : VpwtPBS{r0m5 0W t4x3IB5}
```

Immediately I am suspicious of `Credit` and `Keywords`. I only looked at Vigenère Ciphers before the CTF and one example used a Base64 encoded key haha. I decoded `U3Bhbm5pbmdUcmVlVmlnCg==` to `SpanningTreeVig`, so I plugged that into a Vigenère Cipher solver and out fell the key.


Flag: `DawgCTF{l0t5 0F p4t3NT5}`
