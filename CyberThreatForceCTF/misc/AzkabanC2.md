## Azkaban C2 (200 Points)

### Problem
```
We has find ip of C&C server and client of this. You need to find the all secret in server.

Added (03/07) : The client is in 0.0.1 Alpha is possible problem is present, if client don't work you can use other tools to connect to c&c.

file: client.py
```

### Solution
The challenge simply asks us to find the secrets on the server i.e. the flag.
By creating an Instance and getting an IP Address and Port Number, we can netcat and see what we are greeted with.

```
$ nc 144.217.73.235 25686

[*]BruteForce - Protection
Send result of 461 + 571

```

Okay, very basic math, and I don't seem to be timeboxed here, so I can enter the answer myself without timing out, so I enter `1032`.

```
[*]Password enter pin:
```

Okay, the server wants a PIN. We're supplied with a `client.py` file. Let's examine that for clues.

```python
while (True):
	menu()
	pin_code = "4785"
	teamserver_ip = "192.168.1.19"
	teamserver_port = "9050"
```

I can see near the bottom of the file there is a `pin_code` set to `4785`. Let's try that on the server.

```
Welcome to Azkaban - C2 SERVER
1)Implants connectées
2)Dump creds
3)Credit
```

That was easy. I'm guessing what we want to do is `Dump creds` so lets enter `2`.

```
Dump des pass/hash
____________________________________________________________
| Pass           | Username | Site                          |
____________________________________________________________
| .W$vjDEmV7YR/  | s3rgue1   | 3eRAqbN921ULIRn8.onion       |
 ____________________________________________________________
| CYBERTF{0wn_th3_t3ams3rv3r} | Administrator   | .         |
 ___________________________________________________________
| kuBtV9T}a  | serguei@secret.com | orCcZ6gk4dgPHZOx.onion |
 ___________________________________________________________
 ```

 Wow, we got the flag that easily? 200 points so free.

Flag: `CYBERTF{0wn_th3_t3ams3rv3r}`
