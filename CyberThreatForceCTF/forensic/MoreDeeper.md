## More Deeper (100 Points)

### Problem
```
Can you see what is written in the notepad?
(Use the file downloaded from Deep in my mind)
```

### Solution
I've done this before in previous CTFs so this was easy to complete.

Using `Volatility` we can extract memory dumps by specifying the `PID`. To find the process, we can use `pslist`.

`python vol.py -f mem.raw --profile=Win7SP1x64 pslist | grep notepad`

We can see in the results the PID is `628`.

Then we can use `memdump` to dump the process memory to `628.dmp`.

`python vol.py -f mem.raw --profile=Win7SP1x64 memdump -p 628 --dump-dir=./`

and finally, we can search the `.dmp` file using `strings`

```
$ strings -e l ./628.dmp | grep CYBERTF

CYBERTF{D33P3R_TH4N_TH3_M4R14NN4_TR3NCH}
```

Flag: `CYBERTF{D33P3R_TH4N_TH3_M4R14NN4_TR3NCH}`
