# Functions

To define a function, this uses the *function* keyword and the basic syntax is `function NameForFunction(){code}`.



> [!TIP]
>
> This is not like JavaScript where a function can be declared anywhere do to hoisting. This is like C where it must be declared before being used.



> [!NOTE]
>
> By default, all values passed to functions are passed by value (copy of value and not original) and not pass by reference, but there is a way to do pass by reference.

When it comes to calling a function this is standard like other languages

```php
<?php

function welcome(){
	echo 'Welcome!';
}

welcome();
```



When it comes to adding parameters, this is like JavaScript again where just the name of the variable needs to be placed and no type specified. Of course make sure to add the dollar sign in front of the variable name. To add multiple parameters just separate with comma. Then calling the functions with arguments is the same too like C.

```php
<?php

function function_name($parameter1, $parameter2) {
    echo "$parameter1 and $parameter2";
    $parameter2 = "NOPE";
}

$name = "Jack";

function_name("Smith", $name);
echo $name // still Jack since this is passed by value
```



When it comes to getting a value back, just use the *return* keyword like in C. There is no need to specify a return type just like in python.



> [!IMPORTANT]
>
> PHP does support type hints like python. This is like python where even if the incorrect type is passed in will still work AND this will actually type cast the incorrect argument into the specified data type the function wants. For example, if the function specified it wants a string, but a number is passed in, that number will be converted into a string to match what it was supposed to be. 
>
> However, can more strict where the type specified is enforced at run time and will cause an error if not the correct type. To do this must use the **declare()** function and pass in the value *strict_types=1*. The **declare()** must also be the top most thing in the PHP code and only thing that can come before it is <?php.
>
> If the type requirements are not met then this will return an TypeError object.



## Pass by reference

To have the value be passed by reference so the function can actually change the value and not be a copy, just like with the *foreach* loop, need to put a & in front of the parameter name like `&$parameter`. There is no need to use the **unset()** function to clean up the variable like the *foreach* loop since the function will do this. Give the variables types like in C and to specify the return type do `: return type` right after the closing parenthesis.

```php
<?php
$original_count = 5;

function increment_by_reference(int &$num): void {
    echo "Inside function (Before change): $num\n";
    $num++; // Modifies the original variable $original_count
    echo "Inside function (After change): $num\n";
}

echo "Outside function (Before call): $original_count\n";

increment_by_reference($original_count);

echo "Outside function (After call): $original_count\n"; 
?>
```

Types can be:

- int
- float
- void
- string
- bool
- object
- array
- resource
- null
- mixed --> alias for it being able to be any type

> [!NOTE]
>
> When giving a type, can use two other cool things so that parameter can be multiple types. Can have that parameter be multiple acceptable types by putting `|` between the types like `int|float $x` so x can be a float or int. Can also do ? before the before the type and this means the parameter can be that value and if it is not then make that parameter value *null*. For example `?string $name` so if no string value for that then it then name will be *null*.



## Default parameters

Just like in python, there is a way to set default parameters. This is also done the same exact way like in python where the parameter just needs to be set equal to some value. So if that parameter does not get anything it will always have some value, unless a value is passed in for it then it will use that instead.

```php
<?php

function concat($str1, $str2, $delimiter = ' ') {
    return $str1 . $delimiter . $str2;
}

$message = concat('Hi', 'there!');
$message2 = concat('Hi', 'there!', '-');

echo $message;
echo $message2;
```



*default values* can only be:

- arrays
- raw scalar values (3, "yes", etc)
- null



> [!TIP]
>
> Make sure to put the default parameters all the way in the back as this makes it easier to work with them and allow multiple of them.



## Named arguements

Just like in python, there is a way to use *named parameters*. This give the ability to specify what particular parameter should get the specific value. To do this do `NameOfParameter: value`. 



> [!CAUTION]
>
> Can do some parameters normally and others with named parameters, but rules must be followed to do this. The rule is
>
> --> RULE <--
>
> All possible named arguments MUST come AFTER all normal positional arguments.