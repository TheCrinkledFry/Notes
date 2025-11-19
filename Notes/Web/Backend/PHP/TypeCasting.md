# Type Casting

When it comes to casting a variable from one type to another, since this is like python, it can just be assigned another value from a different type. For example, assigning a variable 30 then assigning it "cool" is valid.



However, to type cast something to a specific type, just put the name of the specific type inside parentheses. For example:

```php
<?php
    $number = "400";
	echo $number;	
	$number = (int)$number;
	echo $number;
```

 

This is the same thing for:

- (string)
- (float)
- (int)
- (bool)