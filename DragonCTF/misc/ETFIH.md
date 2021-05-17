## Encrypted The Flag I Have (100 Points)

### Problem
```
Decrypted flag is not in exact format.
```
![](img/encryptedflag.png)

### Solution
I won't lie, I went the long way on this one.
I plugged this into a font finder because I couldn't find much info after a little bit of digging.
I got a match called `Gonk Droid Medium` and looked that up on [MyFont](https://www.myfonts.com/fonts/edds-aurebesh-fontworks/gonk-droid/), took a look at the glyphs and decoded by hand.

Only after the CTF did I find out that this is a writing system from Star Wars called Aurebesh.

```
Aurebesh was a writing system used to transcribe Galactic Basic, one of the most used languages in the galaxy. In the Outer Rim Territories, Aurebesh was sometimes used alongside Outer Rim Basic, another alphabet.
```

There's even a Aurebesh decoder on [DCode](https://www.dcode.fr/aurebesh-alphabet). I'll know for the future 😅

Anyways, the flag!

Flag: `dctf{MASTERCODEBREAKER}`
