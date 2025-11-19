# Errors

When it comes to coming across errors in code, these are specific events that occur that could be fatal to the program. There are specific types of errors that are thrown depending on the situation.



All errors come from an object called *Throwable* and this is the parent to all other object error types.



[click here](https://www.php.net/manual/en/language.errors.php7.php) to see all available error types and the hierarchy of them



These errors are good when using in *try-catch* blocks so resolve particular types of errors.



```php
<?php
    $x = 40;
    $y = 0;
	try{
        $total = $x / $y;
    } catch (DivisionByZeroError $e){
        echo $e->getMessage();
    }
```

| Function name      | Return Type | Function Description                                         |
| ------------------ | ----------- | ------------------------------------------------------------ |
| getMessage()       | string      | Gets the error message (a human-readable description of the problem). |
| getCode()          | int         | Gets the error code (typically 0 for built-in PHP errors, or a custom code if user-defined) |
| getFile()          | string      | Gets the full path and filename where the error occurred.    |
| getLine()          | int         | Gets the exact line number in the file where the error occurred. |
| getTrace()         | array       | Gets the stack trace as an array, showing the sequence of function/method calls that led to the error. |
| getTraceAsString() | string      | Gets the stack trace as a formatted string (useful for logging). |
| getPrevious()      | ?/Throwable |                                                              |
| __toString()       | string      |                                                              |
