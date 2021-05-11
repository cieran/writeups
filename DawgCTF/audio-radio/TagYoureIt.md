## Tag, You're It! (100 Points)

### Problem
```
Keeping your music library labeled and organized is like a full time job sometimes.

retaliate.mp3: https://drive.google.com/file/d/1xgCTjoBzydbiURCdMMjxEDMq2i9VN1gX/view?usp=sharing
```

### Solution
Hmm okay.. The problem mentioned labels, I can probably see that in the file metadata. I can just use `exiftool`.
```
❯ exiftool retaliate.mp3
ExifTool Version Number         : 12.21
File Name                       : retaliate.mp3
Directory                       : .
File Size                       : 2.8 MiB
...
...
...
Lyrics                          : [Verse 1].I don't know what's going on.I'm feeling weak, but I feel so strong.And I won't fight, and I won't run.Don't need a knife, I need a gun.[Bridge].Don't need a knife, I need a gun.[Chorus].Retaliate, retaliate.Retaliate, retaliate.Retaliate, retaliate.[Syllabic improvisation].[Outro].Retaliate.Retaliate.Retaliate.[Syllabic improvisation].[DogeCTF{wr0te_0ut_th3s3_1yrics_by_hand_1ma0}]
Comment                         : Ḑ̶͙̀á̴̡̳͈̏ẃ̸͇͚g̸̭̣̱͂C̵̹̆̂Ṱ̴̡͍̀F̴̻͚͐̿̄{̴̟̃̀̐w̵̺̻͒̔͋h̴̭͛0̵͍̤͒͆͝_̷̟̈́͘̚d̶͙͕͜͝0̶͕͚͎̏̚w̸̦͙̃̽ǹ̷͙͚l̶̛̜̈́0̴̧̱͓͝a̶̘̮͚̿̈́ď̷̡̬́ŝ̴̢͔̌͝ͅ_̶̬̺͛̎̈́ͅm̵̳͗ű̶͎̊s̷̰̀̄͆1̸͕͖̈́c̶͔͆_̷̢̧̔̉̚â̵̙̔ǹ̵̖̦͈̇̿ỵ̴̬̓̔m̸̛͉̩̑0̸̮͓̏̊̀r̴͇͕̈́̄̉3̶̙̭͎͋̚͝?̴͔̟̩͊͛}̴̤̲͂͜
Date/Time Original              : 2015
Duration                        : 0:03:04 (approx)
```

I see a flag in `Lyrics` but it's prefixed with `DogeCTF` so I'm ignoring it. Ah, look at `Comment`. It's tough to read, but I can manually retype this and validate it. Thankfully, it worked!


Flag: `DawgCTF{wh0_d0wnl0ads_mus1c_anym0r3?}`
