# Data Types

Unlike other languages, but kinda like JavaScript, PHP has different way to categorize data types.

1. Scalar values
   - Integers --> -3, 4, 0, etc
   - Floats -->3.4, -2.0, 0.0, etc
   - Boolean --> true or false or TRUE or FALSE or False or True
   - Strings --> "yes sir" or 'yes sir' will both mean the same thing
2. Compound
   - Array
   - Object
3. Special
   - null
   - resource



## Scalar Types

A *scalar* type is a variable that only hold a single value.



The size of an *int* type depends on the server PHP is running on. The floats are represented with the IEEE 754 standard, which have limited precision.



When it comes to how certain values are represented as false when using things like **if** or **switch** statements, the following represent false:

- *false* keyword
- integer 0 or -0
- float 0.0 or -0.0
- empty string "" or ''
- empty array
- *null* keyword
- SimpleXML objects created from attribute-less empty elements

> [!TIP]
>
> When writing integers or floats, can separate the values with _
>
> So can do something like 1_000_000 or 1_000.05



> [!IMPORTANT]
>
> To make a hexadecimal value must put `0x` in front
>
> To make an octal value must put `000` as these three and + or - in front
>
> To make a binary value must put `0b` and followed by a sequence of 0s or 1s



## Compound Types

A *compound* type is a variable that holds more than one value. There are:

- Array
- Object



### Array

An *array* is an ordered maps that associates keys with values. There are two ways to declare an *array*:

1. Using the normal brackets --> `$Name = [values here]`
2. Using the **array()** function --> `array(values here)`



> [!TIP]
>
> When making an array the values do not need to all be the same type

> [!NOTE]
>
> Can use the function or [], but the [] is more modern and does the same thing using the function for making an array



To access the index of the array it is the same as any other language, but just make sure to put the dollar sign in front of the name.



 Another type of array is called an *associative array*; this is just a hash map. To make one use the brackets and each pair will be made by doing `key => value`.



> [!TIP]
>
> Can have an array nested in another array.



When it comes to adding elements into an array can just do:

- $ArrName[] = val --> this will auto add the value to the end of the array and increase the index by one so that is where it will be
- Manually, if the size of the array is known then can just write to an index that does not exist and assign it a value this this will add the value to that index.



When it comes to removing an element from the array, use the **unset**() function for this. Just pass the array in with the index of the element to remove. This will also decrease the size of the array



To get the size of an array use the built in function **count()**.



For Example

```php
<?php
 $ArrMix = [3, "yes", 4.5];
$ArrSame = [4];
$ArrFunc = array("no", "yes");
$ArrAsso = ["Gabriel" => 50, 120 => "no"];

// Adding elements
$ArrAsso["Mouse"] = "gay";
$ArrSame[] = 40;
$ArrSame[4] = 400;
	
echo $ArrAsso["Gabriel"];
// echo $ArrSame; -->  this is considered wrong and makes error
echo $ArrSame[0];
print_r($ArrMix); // Will display whole array
print_r($ArrAsso); // Will display whole array
print_r(4);

// Removing element
echo "<br/>";
echo "Inital: " . count($ArrAsso);
echo "<br/>";
unset($ArrAsso["Gabriel"]);
echo "<br/>";
echo "After: " . count($ArrAsso);
```



When it comes to multidimentional arrays

```php
<?php

$tasks = [
    ['Learn PHP programming', 2],
    ['Practice PHP', 2],
    ['Work', 8],
    ['Do exercise' 1],
];

print_r($tasks);


```



### Object

This is just an instance of a class. PHP also has OOP principles.



## Special Types

### null

This *null* is just a way to represent that a variable does not have ANY value type.

A variable can be set this by just assigning it the value *null*. However, there is also a built-in function called **unset(variable)** and set that value, regardless of the value it originally had, to *null*.

This is not case sensitive, so can do *null*, *NULL*, *Null*, etc.

To test if a variable is *null*, then use the built-in function `is_null(variable name)`.

### Resource

A *resource* type is just a reference to an external resource like a file, database connection, network connection, etc.

Under the hood this works as just being a reference to the external object; kind of like python with normal objects.
