# While and do-while

When it comes to the *while* and *do-while* loop, this is the same as in C. So this will keep executing the loop while the expression is true. Syntax is `while (condition){code}`.



> [!TIP]
>
> Just like with a if statement, if there is only one line of code to run, can omit the need of curly braces.

## while

```php
<?php

$total = 0;
$number = 1;

while ($number <= 10) {
	$total += $number;
	$number++;
}

echo $total;
```



## do while

This works just like in C where *do* part will execute always and then check condition of while to see if it needs to run again. Syntax is just like C `do {code} while (expression);`



> [!IMPORTANT]
>
> Need to add a semi-colon and end of this loop, but not needed for other while loop.



```php
<?php

$i = 4;
do {
 echo $i;
 $i--;
} while ($i > 0);
```

