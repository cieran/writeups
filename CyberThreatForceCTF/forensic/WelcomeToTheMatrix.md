## Welcome To The Matrix (75 Points)

### Problem
```
Hello Agent, We were able to retrieve a network dump from a VPS belonging to APT403, try to determine the C2 used.
Flag Format: CYBERTF{the name of the c2 in leet and capital letters}
example : CYBERTF{M3t45PL01T}
but T is not in leet

file: c2.pcapng
```

### Solution
Opening our `c2.pcapng` file in Wireshark, we see a bunch of TCP traffic, nothing too interesting. If we follow the beginning of the TCP stream we see some plaintext data which is very helpful to us.

```
..................[..9j.b.6    _3h..Y.gAR..... ...XM.H.QC...(......pzk4h........$.......+./.....,.0.
.    ........./.5.
..............
.......................#...^.....B.~x..C..A:.!..&....?.q..m...9....d...Y}.."lVa......s..'.p.1Ue::..A..[............6......P....YN....P..~.6..    u...e:...:3....p&{..s..B...kU...IAc.sJ:G..Q...$_..qO....p..........h2.http/1.1..........3.k.i... Knc.U..'...LE.2.)...K...N0....S@...A..1...M..-.    N.G..aF.Cz......K.......H..c-}....N.....m.d'..t..+&...+........
...........................-........@.....J...F...5s.}.....(...N.......}<...$.^QJ../.................#.........h2...................0...0.................d0
.    *.H..
.....0.1.0...U....Covenant0..
210520070857Z.
310519070857Z0.1.0...U....Covenant0.."0
```

And on `The C2 Matrix` we can validate that `Covenant` is indeed a C2 Method.

A bit of guess work involved for translating, but this in leet speak is `C0V3NANT`.

Flag: `CYBERTF{C0V3NANT}`
