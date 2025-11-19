# Enumerations

When it comes to creating enumerations, they're declared way differently than something like C and function differently.

## Pure Enum

To declare an enumeration use *enum* keyword followed by the name for the enumeration. Now to declare a value for the *enum*, have to use the *case* keyword followed by the name and then end with a semi-colon.



When it comes to accessing the properties, this uses the :: separator.



One big difference is unlike something like C, the enums here are not integers under the hood and instead are PHP objects.

### Syntax

```php
<?php
    enum animals{
    	case Cat;
    	case Dog;
	}

	$result = animals::Cat === 0 ? true : false; // results in false since Cat is an object and not an integer

var_dump($result);
```



## Backed Enums

To change the default way of having each thing be an object, the values these can be assigned are integers or strings, but not both. Also, every value in the enum will then need to be assigned the respected type or else an error will occur.



To make this, declare the enum the same way like before except

1. Put a colon right after the enum name and then put the data type theses will also be (string or int).
2. Now for each enum case name, set it equal to the respected type specified.



When it comes to using the enums now this will be almost similar to before except one difference. Now have to use the object access symbol -> and then access the `value` property.

```php
<?php
enum animals: int{
  case Cat = 0;
  case Dog = 1;
}

$result = (animals::Cat->value === 0) ? true : false; // results in true since Cat is an integer now

var_dump($result);

```



> [!IMPORTANT]
>
> All the values of an enum are read only so the values of them cannot change and trying to do so will cause major errors even before the thing 