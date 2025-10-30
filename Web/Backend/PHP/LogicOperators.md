# Logic Operators

When it comes to the the logical bitwise operations, this has the common types of:

- and (&&) --> The word way of writing this is the convention to use
- or (||) --> The word way of writing this is the convention to use
- not (!) --> The word way of writing this is the convention to use



When the value of the *and* statement is made, if the first logic operator is false then it will not evaulate the second half; this is called **short circuit**.

```php
<?php
$debug = false;
$debug && print('PHP and operator demo!');
// This will not do the printing as the short circuit from debug will cause this to stop
```

> [!WARNING]
>
> Can evaulate something for a boolean statement even outside of something like a conditional operator. Make sure that this is written correctly.

> [!TIP]
>
> It is common to do something like `dbConnect() or die("bad connection")` as this will make it so if the connection does fail then it will stop the program, but if it passes then it will be ok.

