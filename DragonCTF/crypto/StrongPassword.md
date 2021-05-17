## Strong Password (100 Points)

### Problem
```
Zip file with a password. I wonder what the password could be?
Hint: Don't use fcrackzip
File: strong_password.zip
```

### Solution
Okay, cool, we get a `ZIP` file, we're told not to use fcrackzip, so we can tackle this using `john` or `hashcat`, most likely with `rockyou`.

To pull out the hash:

`zip2john strong_password.zip > strong_password_hash`

To crack the hash:

`john strong_password_hash --wordlist=rockyou.txt`

Show results:
```
❯ john --show strong_password_hash
strong_password.zip/lorem_ipsum.txt:Bo38AkRcE600X8DbK3600:lorem_ipsum.txt:strong_password.zip:strong_password.zip

1 password hash cracked, 0 left
```

The `ZIP` file password is `Bo38AkRcE600X8DbK3600`, we can unzip now and doing a quick search through the `lorem_ipsum.txt`, we can see the flag.

```
❯ less lorem_ipsum.txt | grep dctf
Fusce a sodales mi, quis bibendum metus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; In a est tortor. Ut porta justo risus, a faucibus mi sollicitudin ut. Suspendisse bibendum elementum lectus id dictum. Quisque malesuada libero nunc, a posuere justo bibendum et......
dctf{r0cKyoU_f0r_tHe_w1n}
.....Etiam in volutpat nunc. Aliquam erat volutpat. Ut dapibus, sem at posuere sollicitudin, tellus elit faucibus ligula, ut malesuada leo erat eu sem. Nam nulla lacus, feugiat placerat porttitor eu, sodales quis quam.

```
Flag: `dctf{r0cKyoU_f0r_tHe_w1n}`
