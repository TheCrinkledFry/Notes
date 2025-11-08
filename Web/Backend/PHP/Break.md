# Break and continue

This is functions like normal like any other languages to just leave a loop early. The only thing that is different is it can have a numeric value given to it like a *return* statement and it will leave that many loops from the current place it was called in.



## Break

```php
<?php

$i = 0;
$j = 0;
for ($i = 0; $i < 5; $i++) {
	for ($j = 0; $j < 3; $j++) {
		if ($i === 3) {
			break 2;
		}
		echo "($i, $j)\n";
	}
} // will break out of both of the for loops
```
