## Go Into The Abyss (75 Points)

### Problem
```
Can you see the commands typed ?
(Use the file downloaded from Deep in my mind challenge)
```

### Solution
I got the flag for this chall during the `More Deeper` challenge.

In that challenge I had to find what was written in `notepad`.

Given my dmp file `628.dmp`, I ran:

```
$ strings -e l ./628.dmp | grep CYBERTF

- echo  CYBERTF{W3LC0M3_T0_MY_D35KT0P}
- echo  CYBERTF{W3LC0M3_T0_MY_D35KT0P}
```

Flag: `CYBERTF{W3LC0M3_T0_MY_D35KT0P}`
