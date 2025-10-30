# Switch

When it comes to writing switch statements, this is like in C.



Make sure to write `switch(expression){ cases ...}`

Each scenario will have the *case* keyword followed by the value for that case and then the colon like in C. For that case put all the needed logic and make sure to end each case with the *break* keyword or else this will cause a fall through. This also supports the *default* case.



Can also have the same code work for multiple cases just like in C by putting multiple case blocks stacked on each other



```php
<?php
    $x = 50;
	
	switch ($x){
            // double case stacking here for 20 and 30
        case 20:
        case 30:
            echo "Wrong";
            break; // make sure no fallthrough
        case 40:
            echo "Close but still wrong";
            break;
        case 50:
            echo "Correct";
            break;
        default: // default case
            echo "Broken";
    }
```

> [!CAUTION]
>
> Each cases is also matched loosely, meaning even though the variable is a number with value 50, but a case has a string with text 50 then this would still be considered a match. 