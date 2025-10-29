# Variables



When it comes to creating variables, put a dollar sign and then right afterwards put the name for the variable; do not put a space between the name and dollar sign.



When referencing the variable, this is will be the dollar sign followed by the name.



```php+HTML
<!DOCTYPE html>

<html>
    <head>
        <title>PHP Variables</title>
    </head>
    <body>
        <h1>Introduction to making variables</h1>
        <?php
        	$this = 430; // declaring a variable
        	echo $this; // using the variable
        ?>
    </body>
</html>
```



The naming convention for PHP is camal case.



Variables are case sensitive, so doing `$jack = 40;` and then `echo $JACK` will not work.



When it comes to declaring a constant type, this is not done with the typical *const* keyword, but using the function **declare()**. This function takes two arguments.

	1. The name of the function
	1. The value, which can be any valid value
