# PHP



## What is PHP

When it comes to what PHP can do, this is really used for web development since it can embed HTML code inside the PHP file so this will work just like coding normal HTML file.

> [!IMPORTANT]
>
> For Example
>
> ```php
> <!DOCTYPE html>
> <html>
>     <head>
>         <title>Example</title>
>     </head>
>     <body>
> 
>         <?php
>             echo "Hi, I'm a PHP script!";
>         ?>
> 
>     </body>
> </html>
> ```



The `<?php ?>` tags are like a way to say hey go into PHP mode and process this when seeing the `<?php` and end the processing when the `?>` is seen. Anything that is not inside this block will be displayed and not processed by PHP.



PHP is not a compiled language like C or Golang, but is a scripting language like Python or JavaScript.



One unique thing about PHP is all the code is processed by the server and not by the client like JavaScript is. This means that to process a PHP file, the code must run on a server of some sort and not something like JavaScript that can just run on the localhost system. This is because the server will process all the actual PHP code and replace it with the correct stuff so when it actually gets sent back to the user, they see none of the PHP code and just see HTML code that is was replaced it by the server.



Another thing PHP is used for is CLI scripting. This is useful for running things like CRON jobs since the PHP file does not actually need a server or browser to do this and just need the PHP parser to do this.



> [!NOTE]
>
> When it comes to how PHP installed, there is the base PHP version that will just run on the CLI and output the content through the CLI. However, to have PHP run on a web server, a special version has to be installed called *PHP-FPM*. This special version makes it so the web server and PHP service can communicate with each other. [Click here]([How Nginx and PHP-FPM turn a web request into code](https://www.youtube.com/watch?v=lh4RnczaATI)) to watch a video explaining this.



Another thing PHP is good for is: 

- text processing
- Database handling
- Making web request
- Sending mail
- Data encryption
- Multiple Protocol support



There is a way to see what browser is using by running `echo $_SERVER['HTTP_USER_AGENT'];`. Then can use a function called `str_contains()`. This will take two parameters and they are:

1. The string to check
2. The string to look for EXACTLY.



> [!IMPORTANT]
>
> ```php
> ?php
> 
> if (str_contains($_SERVER['HTTP_USER_AGENT'], 'Firefox')) {
>   echo 'You are using Firefox.';
> } else if (str_contains($_SERVER['HTTP_USER_AGENT'], 'Windows')){
>   echo "You are using Windows";
> } else {
>     echo "Using something else";
> }
> 
> ?>
> ```



### Comments



When it comes to commenting code, this is the same as in C







## Basic Syntax



### PHP Tags

When it comes to even write PHP code, it all must be between the tags **<?php** as the opening tag and the closing tag will be **?>**. Any code outside here will not be recognized by the PHP parser and will not replace that content.



When it comes to wanting to display only a single thing to the screen, use the syntax         `<?= "string here ?>"` as this is the same as `<?php echo "string here" ?>`. Putting the actual **echo** keyword will cause an error to occur.



Since PHP can be used to write a mix of normal HTML code inside it, when coding HTML code inside it like normal, the open and closing PHP tags must be used or else errors will occur. However, if the file will contain ONLY PHP code then it can just have the open PHP tag and that is all.



### Escaping from HTML



When it comes to processing HTML and PHP code, when the PHP parser sees the `<?php` then it enters a special state that it knows this is code to process. and once it sees the closing    `?>` then it goes into the special mode that just outputs everything it sees. Another state is when it evaluates something like a control block and the logic comes back false, then it enter another state that will skip ALL things it sees until it reaches another control block like else or the closing }.



There is a special syntax that can be used to control the logic of what is outputted, which will be learned later, but here is a reference to it.

> [!IMPORTANT]
>
> ```php
> $expression = true;
> 
> <?php if ($expression == true): ?>
>   This will show if the expression is true.
> <?php else: ?>
>   Otherwise this will show.
> <?php endif; ?>
> ```



> [!WARNING]
>
> It is required to added a semi-colon at the end of each statement in PHP.





## Types



###  Data Types



The data types in PHP are:

- null
- bool
- int
- float
- string
- array
- object
- callable
- resource



Since PHP is a dynamically types language, there is no need to specify the data type like in Python. However, just like Python, there is a way to give a hint on what data type something should be. There is even a way to set something so is it required to give data types.



> [!NOTE]
>
> There are other ways to specifically declare the type of a variable and that is using the **settype()** or using type casting. The **settype()** will take two parameters with the first one being the name of the variable and the second will be the variable type and this will be entered as a string of "bool". "string","int", "float", "array", "object", or "null". An important thing to note is the variable can or cannot exist when passing in the variable name.       `settype($yes, "int");`. Type casting is done by surrounding the needed data type in parenthesis and the putting that in front of the variable name like `$x = (string)$y` and all the same types that are passed to `settype()` are the same for this.



```php
<?php
  $whole = 40;
	$dec = 4.2;
	$str = "yes"; // using single quotes is the same thing
	$dec = true; // can also be false
```



There is a special function called **var_dump()** that takes a single parameter and that parameter any variable type and this will give back the data type of it and the value it has.



> [!TIP]
>
> There is a way to check is a variable is a specific type by using a function is_{type}() where type is the variable type like: bool, string, int, float, etc. For example like            `is_int()`



When it comes to trying to work with two different data types, something like adding a float to an int, PHP does something called **type juggling**. **Type juggling** occurs in a few different contexts:

#### *Numeric* 

This is when if either variable is a float, then the int variable will automatically be converted into a float and the result will be a float. Otherwise, both will be interpreted as an int and result in an int.

```php
<?php
  $momey = 40;
	$pay = 34.99;
	$result = $money - $pay; // This will result in a float result
	
	$momey = 40;
	$pay = 34;
	$result = $money - $pay; // This will result in a int result
```



#### *String*

This is when working with the **echo**, **print**, **string interpolation**, or **string concatenation** operations will the variable be turned into a string.

```php
<?php
	$money = 50;
	echo "current money is: ".$money; // will convert $money to a string
```



#### *Logical*

This is when working with something like the the **ternary operator** or the logical operator **if**.



#### *Integral and String*

This is working with bitwise operations



#### *Function*

If the value passed into the parameter is not the exact type then it will be converted into the needed one.



### Type System



When it comes to identifying a variable type, each one is placed into a certain category:

- Scaler
  1. bool
  2. int
  3. float
  4. string
- array
- object
- resource
- never
- void
- relative class type
- singleton type
  1. false
  2. true
- unit type
  1. null
- user defined types
  1. interface
  2. class
  3. enumeration
- callable



> [!NOTE]
>
> There are two other special types called *mixed* and *iterable*. These mean of                  `object|resource|array|string|float|int|bool|null` and `Traversable|array` respectively.



### Strings



There is a special way to make strings called *heredoc* string. These are special strings that basically work like normal double quoted strings. This are also declared differently compared to normal strings. These require the the text to start with `<<<CustomName` and then end with  `CustomName`. This custom can be anything, but should be named something to describe what the string will be.



> [!IMPORTANT]
>
> ```php
> <?php
>   $str = <<<HTML
>   <div>
>   	<h1>This is better</h1>
>   	<p>Small test</p>
>   </div>
>   HTML;
> ```









# Built In Functions

| Function name | Parameters                                                   | Return Type                                                  | Use Case                                                     |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| settype()     | 2 parameters needed. The first is the variable name that can or cannot be declared already. The second is the data type this will be and this will be passed in as a string. The values can be "bool". "string","int", "float", "array", "object", or "null". | This will return the data type in the converted version.     | This is used to set a variable to specify the data type of it. |
| var_dump()    | 1 parameter needed. This will be any variable                | This will return in a string form the data type and value of the variable | This is used to get information about a variable.            |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |
|               |                                                              |                                                              |                                                              |

