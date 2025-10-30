# Try-Catch 

When wanting to test with some possible dangerous code that could result in a fatal error, it is best to use a *try-catch* block. This is a way to catch fatal errors and handle them gracefully rather than have them crash the code.



To use this make two separate blocks like:

```php
try{
    //code here
} catch(){
    // code here
}
```

The *try* block does not take any arguments as this is just gonna be the area where code is tested so nothing is passed to this. However, for the **catch()** portion, this could or could not need a parameter. If the code were to throw an error ONLY THEN will the **catch()** block will go off, otherwise if all is good then the **catch()** will never execute.

> [!TIP]
>
> Multiple **catch()** blocks can be added to the simple try-catch structure. This will make it so errors of different types can be resolved different ways



The argument the **catch()** will take is a type from the built in object *Throwable* which is used to handle errors.



There is one more block called *finally* that is set up like the *try* block except all code written in there will ALWAYS execute no matter the situation of the *try-catch* statements. Meaning if this passes or fails that section of code will always execute.



> [!NOTE]
>
> Reference the errors.md file to see all available error types and methods.



```php
<?php
    $x = 40;
    $y = 0;

    try {
        $total = $x / $y;
        echo "Divided correctly";
    } catch (DivisionByZeroError $e){
        echo "Error stoped gracefully";
    }
```



## Custom Errors

All custom errors must inherit the class *Exception*.



Creating a custom error type gives the ability to keep track of custom cases where a particular error needs to be caught.

```php
<?php

// Custom class must extend the built-in \Exception class
class InsufficientQuantityException extends Exception {
    // Optional: Can override the constructor to force certain parameters
    public function __construct($message = "The requested quantity is insufficient.", $code = 400, Throwable $previous = null) {
        // Call the parent Exception constructor
        parent::__construct($message, $code, $previous);
    }
    
    // Optional: Add custom methods for more details
    public function getMinimumRequired() {
        return 1;
    }
}
?>
```



## Throw

There is a special keyword called *throw* and this is a manual way to trigger an error to be thrown. For example, if wanting to trigger an error if the resulted value equal four.



To *throw* an error the syntax is `throw new ErrObjType(parameters here);` and this will cause the program to go into some error mode that needs to be handled.