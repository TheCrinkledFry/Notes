# Builtin Functions

1. `define("const name", any value)` --> This will create a constant at runtime unlike using the normal *const* keyword which can only be done at compile time.
2. `var_dump(variable name)` --> This will return information about the variable passed in like value assigned to it and data type. This will not tell if it is a constant or not.
3. `die(optional single argument)` --> This is used to stop the execution of the program right there and then. This is an alias for another function called **exit()**. Calling either of these functions will do the same thing.
4. `array(any number of arguemnts)` --> This is used to make an array
5. `is_bool(boolean variable)` --> This is used to check if the variable is of a Boolean type. Will return 1 if it is and 0 otherwise.
6. `is_int(integer variable)` --> This is used to check of the variable is of an integer type. Will return 1 if it is and 0 otherwise.
7. `is_float(float variable)` --> This is used to check of the variable is of a float type. Will return 1 if it is and 0 otherwise.
8. `is_string(string variable)` --> This is used to check of the variable is of a string type. Will return 1 if it is and 0 otherwise.
9. `strlen(string variable)` --> This is used to get the length of a string
10. `unset(variable name)` --> This will set the variable to *null* regardless of its original value.
11. `is_null(variable name)` --> This is used to check of the variable is of a null type. Will return true if it is and false otherwise.
12. `declare(flag to set)` --> This is used to set specific special execution directives for how PHP should run. This is mainly just used to set the strict type mode on by passing in *strict_types=1*.
13. `strpos(string to find, text to look in)` --> This is used to see if another string contains the string to look for. This will return an int of the position the first letter where it starts in the string found in. This will return bool false if not found. 
14. `sprintf(string, value(s))` --> Used for string formatting like in C and this returns the string instead of printing it. Use the exact delimiters (%s, %d, ...) like in C. First have the string and then the rest of the arguments (just like in C) will be the values to go there.
15. `strtoupper(string)` --> returns the string passed in, but all character in uppercase.
16. `filter_var(data, filter type, optional flag)` --> This is use to validate or clean some data. The first two parameters are needed.  Arguments:

    1. Data to be clean/validated
    2. Clean/validate type
    3. optional flags

    When it comes to doing validation the values will be:

    - FILTER_VALIDATE_EMAIL --> Checks for a properly formatted email address.
    - FILTER_VALIDATE_URL --> Checks for a valid URL (requires scheme, e.g., http://).
    - FILTER_VALIDATE_INT --> Checks if the value is a valid integer like "42" or 42
    - FILTER_VALIDATE_IP --> Checks for a valid IPv4 or IPv6 address.

    When it comes to doing cleaning the values will be:

    - FILTER_SANITIZE_EMAIL --> Removes characters illegal in an email address.
    - FILTER_SANITIZE_URL --> Removes characters illegal in a URL.
    - FILTER_SANITIZE_NUMBER_INT --> Removes everything except digits, plus, and minus signs
    - FILTER_SANITIZE_FULL_SPECIAL_CHARS`-->`HTML-encodes characters like `<` and `>` to prevent XSS attack

17. `print_r()` --> This is used to print any data type in a human readable format. A good use of this is printing all contents of an array as using **echo** will cause a fatal error. This can even be used to print things like objects. 
18. `count()` --> specifically used to get the size of arrays or the number of properties in an object that implements the *Countable* interface.
19. ``
20. ``