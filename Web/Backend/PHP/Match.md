# Match

The *match* is a different version of the *switch* statement since this can evaluate case as Booleans compared to having them be strict values; this is where the *match* comes in.



One way *match* differs from *switch* is match will return the value (if done). In *switch* there needed to be a variable made to hold the value returned. For example, a *match* case would be better for returning something from a function instead of having to create an extra variable, which would take more data, and return that.



Another benefit of *match* is each case can also be a Boolean expression. So can have the value to match be true and each case can be some true or false expression and whichever test true will run.



To use the *match* do `match(value to text)`. There is not case statements for this. Instead it uses the syntax `value(s) => code to run`. There can be multiple different cases that run the same code and this can be done just be separating the code values with a comma. To end each case section just end the whole thing with a comma and start a new case thing on a new line. This can still have a *default* case by instead of putting some type of case value, just and the word *default* and that will function like before with the *switch*.



```php
<?php
    $name = "Gabriel";

	$result = match($name){
        "Nathen", "Jack" => "Wrong names",
        strlen($name) === 7 => "Same number of letters",
        "Gabriel" => "Correct name",
        default => "Error",
        
    }; // closing curly brace here
```

> [!IMPORTANT]
>
> Unlike with switch where there was no ending semicolon needed at the closing curly brace, a match statement does need it.

> [!IMPORTANT]
>
> Make sure to end each case with a comma