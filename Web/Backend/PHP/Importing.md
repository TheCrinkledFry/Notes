# Importing

Instead of having all the PHP logic embedded into a html file, as this makes things harder to maintain, they can be separated into different files. There are two different ways of importing code from one PHP file to another:

1. **include**
   - If the file does not exist a warning shows, but does not stop execution.
2. **require**
   - If file does not exist, an error shows and does stop execution.



## Example

*function.php*

```php
<?php
// A sample function from a file called function.php
function greet($name) {
    return "Hello, " . $name . "!";
}
```

*index.php*

```php
<?php
// Include the function file
include 'functions.php';

// Now can use the greet function
echo greet("Alice"); // Output: Hello, Alice!
?>
```



Can replace the **include** with the **require** and same effect will happen.



When Just like JavaScript, this just add that EXACT code from that file into the other file in that spot.



- Ok, so using **include** is best when there is a template of html or php or both that needs to be reused over and over again; like a php file that makes a button so I could just have a loop that executes "include button.php;" over and over. However, if the file does not exist this does not necessarly mean the site will break, but will look weird or miss some minor non-critical functionality.

- When it comes to the **require**, this will make it so this can also act as a template to the php file this is getting pulled from, but this is more important since this should be holding things like functions, classes, etc. If these are declared more than once then an error can occur, so this does not let the file be declared more than once and it it is then an error occurs and program stops.

- When using **include_once**, this makes it so if this non-critical thing is added to the file lets say like a title bar, where not having this won't break the functionality but should not be added more than once either.

- The **require_once** is just like a more strict version of **require**. But, if this would be added more than once this would not crash the site because it just won't be added.