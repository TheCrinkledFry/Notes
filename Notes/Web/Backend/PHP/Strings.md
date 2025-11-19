# Strings

When it comes to string, there are four ways to declare them

1. single quoted
2. double quoted
3. heredoc
4. nowdoc



The single and double string function in the almost the exact same way except a few differences:

- Double can have values evaluated inside
- Double can interpret things like \n, \t, etc



Unlike other languages that use the plus sign to concat strings, PHP uses the dot. For example:

```php
<?php
    $name = "John";
	$text = $name . " is a cool person"; // John is a cool person
```



The only difference between double and single quoted strings is variables added to the double quoted string can be evaluated.

```php
<?php
    $name = "John";
	$wrong = 'Good job $name'; // Good job $name
	$right = "Good job $name"; // Good job John
	$rightSingle = 'Good job ' . $name;
```



Since a string is just a collection of characters, each character can be accessed individually using the array syntax on it.

```php
<?php
	$name = "John";
	$letter = $name[0];
	echo $letter;
```



To get the length of a string, use the built in function **strlen(string variable)** where this takes a single string variable as an argument.

`strlen($name);`



Now when it comes to using *heredoc* and *nowdoc* strings, these are used to write multi-line strings that do not need special escaping. The *heredoc* strings function just like a double quoted string where can do evaluation of variables and escape sequences. Once unique thing about this is the ability to use single and double quotes without needing to escape them.



To make a *heredoc* string, first put `<<<` and then either HTML, SQL, or EOL, etc as the identifier right after it. The identifier can really be anything as this is more just a mental way to say what that multi-line string is supposed to be for. Then to mark the end of this is put the same identifier at the end with semi-colon to end it.

```php
<?php
    $text = <<<HTML_CODE
    <p>This is a set of text in p tags</p>
    <div class="btn-class">
    	<p>some more stuff here</p>
    	<button>Submit</button>
    </div>
    HTML_CODE
```



Now the *nowdoc* string type is just like the single quoted string except they can be used on multi-lined strings. This is declared the exact same way as a *heredoc* string except wrap the identifier in single quotes. This applies only to the opening identifier and not the closing one

```php
<?php
    $text = <<<'HTML_CODE'
    <p>This is a set of text in p tags</p>
    <div class="btn-class">
    	<p>some more stuff here</p>
    	<button>Submit</button>
    </div>
    HTML_CODE
```

