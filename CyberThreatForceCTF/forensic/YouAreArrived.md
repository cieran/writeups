## You Are Arrived (100 Points)

### Problem
```
What is the flag hidden in the visited  github?
(Use the file downloaded from Deep in my mind)
```

### Solution
The challenge asks for the flag hidden in the GitHub repo.
I grepped `github` on the `.dmp` file from previous challenges and got a URL to a GitHub repo.

I looked through the commit history and there is a key in a file from an old commit: `Q1lCRVJURntUSDROS19ZMFVfTDFOVTVfRjBSX0cxVH0K`

`CyberChef` notices this is just `Base64` which decodes to `TH4NK_Y0U_L1NU5_F0R_G1T`.

Flag: `CYBERTF{TH4NK_Y0U_L1NU5_F0R_G1T}`
