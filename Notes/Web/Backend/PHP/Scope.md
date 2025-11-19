# Scope

When it comes to the scope of variables, this is slightly different compared to other languages. The four scope types are:

- local
- global
- static



## Local

An example of a local variable is defining it inside a function. It will only be valid inside that function and no where else



## Global

This is unique in that this can be accessed anywhere inside the script EXCEPT inside a function.

```php
<?php

$message = 'Hello';

function say() {
	$message = 'Hi'; // does not change value or create variable
	echo $message; // prints nothing
}

echo $message; // Hello
```

However, there are two ways to access global variables inside a function 

1. Putting the *global* keyword before the variable name.
2. Using the *$GLOBALS* array

```php
<?php

$message = 'Hello';

function say() {
	global $message; // give access to variable inside function
	echo $message; // Hello
}

function say2() {
	echo $GLOBALS['message']; // Hello
}

say();
say2();
```



## Super Global

There are some special variables called *superglobal* that are just predefined variables, but can be accessed from ANYWHERE.


Reference the BuiltinTypes.md to see a list of these and what they do



## Static

This are variables that persist outside of a function call so their value still exist. When the function is called again then it will still remember the value the static value had before.

> [!WARNING]
>
> These can only be declared inside functions



```php
<?php

function get_counter() {
    static $counter = 1;
    return $counter++;
}

echo get_counter() .  '<br>'; // 1
echo get_counter() .  '<br>'; // 2
echo get_counter() .  '<br>'; // 3
```



## Variadic functions

This gives the ability to have a function any number of arguments and there are two ways to do that:

1. Using **func_get_args()** --> will return an array of all arguments passed into the function. However, this is an older way. There is no need to put any parameters in the function and when calling the functions there can be any number of arguments. 
2. Using ... --> Put this in front of the variable names.



```php
<?php
    function funcMethod(){
		$args = func_get_args();
    	foreach ($args as $item){
            echo $item . <br/>;
        }
	}

	funcMethod("Yes", "No", 4, 5,6.5);
```

```php
<?php
        function funcMethod(...$args){
    		foreach ($args as $item){
            	echo $item . <br/>;
        	}
		}
		funcMethod("Yes", "No", 4, 5,6.5);
```

> [!NOTE]
>
> Can put other positional parameters along the ... variadic parameter, but this needs to be the last argument in the function.
