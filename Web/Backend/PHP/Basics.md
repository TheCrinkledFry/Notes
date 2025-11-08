# Basics



PHP is more of a template language compared to something like a scripting language. Although it is parsed like python, it does not "execute" all code it scans and will only execute specific PHP code.



A PHP file almost acts as a replacement for html files. Inside a PHP, writing html inside it like a normal html file will be ok. The only difference is this will have the extension *.php*.



A very unique thing about PHP is it *NEEDS* a server with PHP installed to run at all, unlike like something like JavaScript. If these requirements are not met then the server will not know how to parse the file and return the needed information.



When wanting to write the PHP code, it will require having **<?php?>** inside. This is the only tag that is needed and all code will go in between them like:

```php
<?php
	// php code here
    echo "Hello world";
    echo "<p>This was added through PHPs</p>";
?>
```

 

If the file contains ONLY PHP code, then only need to put **<?php** at the top of the file and no **?>** is needed



The `echo` command will output some string(s) to the browser. This can be simple regular text strings or even things like html elements (this html elements will be added EXACTLY as put).



When it comes to where the PHP code is added, just like JavaScript, this fully depends where in the file this PHP code is added as that is where the stuff will be added.



To write a commit or multiline commit, it is the same as C/C++



Make sure to always put a semi-colon at the end of a line



All things listed before are case insensitive and anything not listed is case sensitive:

- Functions
- keywords *true* and *false*
- Class names
- logic statements
  - if
  - else-if
  - switch
  - while
  - do-while
  - for
  - foreach



White space does not have a special meaning in PHP, so doing the following are the same thing:

```php
login(
    $username,
    $password, $age
);

login($username,$password, $age);
```

