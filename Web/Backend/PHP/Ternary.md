# Ternary

This is just an alternative way to write the if statements using the ? sign and the syntax is `$variable = condition ? true result : false result;`

### Ternary Single

```php
<?php
  $x = 40;
  $total = ($x === 40) ? "Correct": "Wrong";
  echo "Item Price: " .  ($x > 20 ? "Expensive" : "Affordable");
```



### Nested Ternary

Can do nested ternary by just putting another within one of the conditional statements.

```php
<?php
  $x == 40;
  $CanBuy = ($x === 40) ? 
      ($x >= 10 and $x >= 35) ? true : false
      : "Error";
```

> [!TIP]
>
> Can separate these on separate lines to make it easier to read.
