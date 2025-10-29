# Constants

Unlike normal languages that use a *const* keyword, PHP does need do that. Instead, it uses a function called **define()**. This function takes two arguments:

1. The name of the constant to have

2. The value the constant will be assigned. The value can be:

   

   | Can Use         | Cannot Use     |
   | --------------- | -------------- |
   | Number          | Variables      |
   | Float           | Objects        |
   | String          | Function Calls |
   | Array           |                |
   | Other Constants |                |



Just like a variable, the naming sensitivity is the same like variables. However, the biggest difference is NOT using the dollar sign in front of the constant name. This can just be written out like normal. In fact even putting the $ in front of the constant variable will make it not work.



The naming convention for constants will have them be in all caps and if it is multiple words then seperate with _



There is a keyword called *const* that can be used, but this can only be assigned values that do not need to be calculated at runtime. If the value does need to be calculated at runtime then use the **define()** function. However, using *const* will make it defined at compile time.



```php
<?php
  define("Apple", 30); // Defines a constant called Apple

  echo $Apple; // this will not work and does not display the value 30
  echo Apple; // this will work and display the value 30
  
  define("APPLE_TOTAL", "Six");
echo $APPLE_TOTAL;
echo APPLE_TOTAL;

const NAME = "Gabriel Centeno";
 const NAME_FIRST = "Gabriel";
const NAME_LAST = "Centeno";
```



