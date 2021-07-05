## Deep In My Mind (75 Points)

### Problem
```
Hello Agent, We were able to get our hands on the RAM dump of a pc belonging to APT403, Find us the potential profile (volatility profile) of the memory dump

format of the flag: CYBERTF{volatility profile}

file: mem.raw
```

### Solution
I've used `Volatility` in previous CTFs, so this was easy for me to do.

```
$ python vol.py -f mem.raw imageinfo

Suggested Profile(s) : Win7SP1x64, Win7SP0x64, Win2008R2SP0x64, Win2008R2SP1x64_24000, Win2008R2SP1x64_23418, Win2008R2SP1x64, Win7SP1x64_24000, Win7SP1x64_23418
```

I tried the first one, `Win7SP1x64`, and it worked!


Flag: `CYBERTF{Win7SP1x64}`
