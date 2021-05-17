## Hidden Message (100 Points)

### Problem
```
This image looks familiar...

Image: fri.png
```
![](img/fri.png)

### Solution
We're given a `PNG` file with a very vague description. The challenge title is `Hidden Message` so my go to is to use a tool like `zsteg` to see if there are hidden messages.

```
❯ zsteg fri.png
b1,rgb,lsb,xy       .. text: "dctf{sTeg0noGr4Phy_101}"
b3,g,lsb,xy         .. text: "I@4I)$Xl"
b3,abgr,msb,xy      .. text: "v\rWv)WvM"
b4,r,lsb,xy         .. text: "\nfb@DHfBHH"
b4,r,msb,xy         .. text: "E`@Q'g3@D@tr"
b4,g,msb,xy         .. text: "ND@&B$rp"
b4,b,lsb,xy         .. text: "D\"$ \"\"\"$bN"
b4,b,msb,xy         .. text: "DDD$Fr0U3p@f"
b4,rgb,lsb,xy       .. text: "HDd(\"b(Dd\""
b4,rgb,msb,xy       .. text: "GpD@FdD#"
b4,bgr,lsb,xy       .. text: "H$b(\"dH$`"
b4,bgr,msb,xy       .. text: "t@@DFd$#"
b4,rgba,lsb,xy      .. text: "`OP/S/b/b?"
b4,abgr,msb,xy      .. text: "O@OdOdO2/"
```

A very easy intro-to-steganography challenge for anyone not familiar with the area.

Flag: `dctf{sTeg0noGr4Phy_101}`
