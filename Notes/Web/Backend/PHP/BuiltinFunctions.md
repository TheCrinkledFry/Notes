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

19. `fopen(file name, mode)` --> opens and returns the file resource if it exist and returns false if it fails

20. `fclose(file resource)` --> Closes the file resource and removes the lock that PHP places on it. Returns true if closed and false if not.

21. `fread()` --> 

22. `fwrite()` --> 

23. `json_encode()` --> Takes one parameter, typically an associative array, and returns a JSON-encoded string if successful, or false if encoding fails.

24. `json_decode()` --> Takes four parameters max. The first is of type string with the string being in a string format. The second is a boolean value for how the return data should be encoded, false for retuns PHP object and true retuns associative array; by default this is set to false. The third and fourth are not really needed to be worried about and just leave them as is.

25. `empty()` --> This takes a single parameter with a parameter bring the name of a variable or array index. This function will check if the value is not set to something. This means that it will return true if the value does not exist, set to null, or if the value has the respected zero value (0 for int, "" for string, false for boolean, etc). All other cases will return false.

26. `isset()` --> This takes a single parameter with the parameter being the name of some variable or index in an array to see if it exist AND if it is not null. This will return true if 

27. `unset()` --> This will take a single parameter with the parameter being the name of a variable or array index and set its value equal to null 

28. `` --> 

29. `` --> 

30. `` --> 

31. `` --> 

32. `` --> 

33. `` --> 

34. `` --> 

35. `` --> 

36. `` --> 

37. `` --> 

38. `` --> 

39. `` --> 

40. `` --> 