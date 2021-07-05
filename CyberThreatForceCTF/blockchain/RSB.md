## Reverse Solidity Bytecode (150 Points)

### Problem
```
But what the hell is this file?

Our agent found this file, can you reverse it and find the secret?

file: challenge.bytecode
```

### Solution
We're asked to reverse some **Solidity Bytecode**. I don't know how to do that, but there of course will be a website online to do that.
After a quick Google search I found [ethervm](https://ethervm.io/decompile).

I decompiled the bytecode and began to examine it. The first thing I noticed was that inside the `func_0140()` function, there were a lot of nested `labels` and padded hex values for each.

The first I saw was `0x4300000000000000000000000000000000000000000000000000000000000000`. And we know that `0x43` in hex is `C` in ascii.

The second I saw `0x5900000000000000000000000000000000000000000000000000000000000000`. And we know that `0x59` in hex is `Y` in ascii.

The rest of the process is obvious, I won't bore you with the repetition.



Flag: `CYBERTF{I_LIk3_R3VeRSe_S0l_!}`
