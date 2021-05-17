## Simple Web (100 Points)

### Problem
```
Time to warm up!
http://dctf1-chall-simple-web.westeurope.azurecontainer.io:8080
```

### Solution
We are shown a checkbox with the label `I want flag!` and a `Submit` button.

Checking the box and submitting returns `Not Authorized`.

Let's look at the HTML...

```HTML
<form action='flag' method='post'>
    <fieldset>
        <input type="checkbox" name="flag" value="0">
        I want flag!<br>
        <input hidden name="auth" value="0">
        <input type='submit' name='Submit' value='Submit' />
    </fieldset>
</form>
```

You can see there is a hidden input field called `auth` with a value of `0`. Why don't we set this and `flag` to `1`, and submit again?

```
There you go: dctf{w3b_c4n_b3_fun_r1ght?}
```

Nice.

Flag: `dctf{w3b_c4n_b3_fun_r1ght?}`
