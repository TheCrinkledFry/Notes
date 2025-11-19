# DateTime

This the modern way in PHP to handle date and time related information;  that is using the *DateTime* object.



When first creating this, it does not need to take any parameters because if none are passed in then that object will get the current date and time automatically.



```php
<?php
    $now = new DateTime();
	echo $now;
	echo $now->format("m/d/y H:i:s A");
```



The important method to know is the **format()**. This is used to get the current time in a string format. Use the following to make a custom way to display:

-  Y --> Displays year fully
- y --> Displays shorthand year
- m --> Displays month numeric
- M --> Display month 
- d --> Displays day of month numeric
- D --> Display actual day
- H --> Displays hour
- i --> Displays minutes
- s --> Displays seconds

- A --> Displays if it is AM
