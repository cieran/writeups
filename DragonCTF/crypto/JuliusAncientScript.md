## Julius' Ancient Script (100 Points)

### Problem
```
I found this Ancient Roman papyrus. Could you decypher it for me?

rq7t{7vH_rFH_vI6_pHH1_qI67}
```

### Solution
First, I will tell you my solution during the CTF, and then I will tell you the intended solution.
Given the challenge title, I obviously went to the most solid encryption known to man - the Caesar Cipher.

`+14` shift using the standard alphabet gives you
`dc7f{7hT_dRT_hU6_bTT1_cU67}`

It was late at night, I was very tired, but I sat there very confused for a while.
I figured that as we know the flag format is `dctf{}`, we can infer..

```
7 -> t
6 -> s
1 -> n
```

so now we have `dctf{thT_dRT_hUs_bTTn_cUst}`.

I figured at this point the flag was `dctf{the_dye_has_been_cast}` and tried to submit it but I was incorrect.

I had to call for backup. I spent 15 minutes trying to explain to my girlfriend the history of the Caesar Cipher and how its rotations work so maybe she could figure out what the capital letters were mapping to. I looked a bit like Charlie in that episode of Always Sunny...

![](img/pepesilvia.jpg)

We gave up for the night, it was almost 2:00am so I went to brush my teeth, cogs still turning in my head. Then it clicked, the capital letters mapped to numbers. Earlier I thought `T -> e` but really `T -> 3` therefore `R -> 1` and `U -> 4`.

Finally, the flag was `dctf{th3_d13_h4s_b33n_c4st}`.

After the CTF I saw people share their solutions and of course it's very very simple with no brainpower required. You can just include numbers in your alphabet (`abcdefghijklmnopqrstuvwxyz0123456789`) and maintain the +14 shift and you get the flag. Ha.

I think my girlfriend deserves an honorary DCTF award for listening to me talk about nothing but ciphers at 2am.

Flag: `dctf{th3_d13_h4s_b33n_c4st}`
