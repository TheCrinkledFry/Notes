# Namespaces

By default, when anything like a function, class, and constant is added from a different file, they're added into the *global namespace*. This is how the file that obtains the code from the *include* thing knows how to reference those.

This is a way to organize classes, functions, and constants so there is no name collision when it comes to giving names to things. This is like when two different files are being included and they both. for example, have functions named add(). If these two are now added into the *global namespace* then this will cause a fatal error to occur because the function is being defined twice. To solve this make a custom *namespace*.

A namespace is like a custom virtual folder that is used to store functions, classes, and constants in and reference them and, most important, be able to have different functions with the same name in the same file.

To make a namespace use the *namespace* keyword. This must also be define before the code, but after the **define()** if used. This will go inside the file that is being created to be imported. Syntax is `namespace name;`.



Once the namespace is made, to use it in the other files, have to use the namespace name separated by \ to access the content from there.

```php
<?php
    // This will be a file named test.php
    namespace testing;

	function adding($x, $y){
        return $x + $y;
    }
```

```php
<?php
// This file is index.php and will include the test.php file
require_once "test.php";
    
//$total = adding(1,2); --> error since not in global namespace
$total = testing\adding(1,2); //--> works good;
    
function adding($x, $y){
   return $x + $y * 3;
}

$total = adding(1,2); // works now and uses one in global namespace
```

> [!IMPORTANT]
>
> When creating the namespace in the other file, can have a nested namespace by just giving the name like `namespace nest\me;` so the add function would now be accessed like `nest\me\adding(1,2);`



> [!NOTE]
>
> It is a standard to give the *namespace* name the path to the file. So put the whole directory path until file is reached as the name.



## Pull into scope

When it comes to adding namespaces, if only certain things are wanted, then it is smart add the *use* keyword. This gives the ability to pull something particular out of the namespace it is in and add it to the *global namespace*.

> [!IMPORTANT]
>
> if the *use* keyword is done by itself then by default it will assume the thing being pulled is a class. However, to pull something like a function or constant, add the keyword *function* or *const* AFTER the *use* keyword. However, this is not recommend to do and bad practice.



```php
<?php
    // This will be a file named test.php
    namespace testing;

	function adding($x, $y){
        return $x + $y;
    }

	function subtracting($x, $y){
   		return $x - $y + 3;
	}
```



```php
<?php
// This file is index.php and will include the test.php file
require_once "test.php";
use function testing\subtracting()
//$total = adding(1,2); --> error since not in global namespace
$total = testing\adding(1,2); //--> works good;
    
function adding($x, $y){
   return $x + $y * 3;
}

$total = adding(1,2); // works now and uses one in global namespace

// $result = testing\subtracting(1,2); --> before being pulled out of namespace
$result = subtracting(1,2); // use keyword pulled into global namespace now
```

