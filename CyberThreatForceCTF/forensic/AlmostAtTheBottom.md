## Almost At The Bottom (100 Points)

### Problem
```
Which twitter account did the user visit?
for the flag, we want the twitter account name without @ For Example:
CYBERTF{elonmusk}
(Use the file downloaded from Deep in my mind)
```

### Solution
For another Forensic challenge, I had to find out what was written in `notepad`.
Because of this, I had a dmp file called `628.dmp` which I got using Volatility.


`strings -e l ./628.dmp | grep twitter`

This returned the following some unnecessary info, but also this:
```
https://twitter.com/GagarineI
https://twitter.com/GagarineI
https://twitter.com/GagarineI
https://twitter.com/GagarineI
https://twitter.com/GagarineI
```

Flag: `CYBERTF{GagarineI}`
