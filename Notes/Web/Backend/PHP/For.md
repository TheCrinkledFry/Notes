# for and foreach

There are two different way to do a for look in PHP.

- Classic C way
- Range based for loop



> [!NOTE]
>
> However, this also have Go like functionality where some (or all) parts of the *for loop* can have parts missing and still function correctly.

## Classic C way

### Normal way

Has the same format as in C with `for (start;condition;increment){}`and this will function like a normal *for loop*.



### Missing all parts

Writing something like `for (;;)` will basically function as a while loop that has no ending condition so to leave it the use of the *break* keyword is needed.



### Missing increment

If can leave the increment part out like `for(start;condition;)`. This will make it so there could be more complex increment cases. For example, if the value is greater then four increment by three and if less than four then multiple index by two.



### Missing start

Having something like `for (;condition;increment)` will make it so can use a variable declared outside of the loop be used as the increment value.



### Missing condition

If the condition, then this is where the loop can still run and this will make it so this will go on forever until the *break* keyword is used.



> [!NOTE]
>
> Other cases to go over, but general point is made and any amount of any combination of them can be missed 





## foreach way

This is another way to go through a loop of something, but best used on a collection of something like going through an array. This is like in C++ doing the `for (int x : numbers)` where numbers is an array.



There are two ways to write a *foreach* loop for the normal array and associative array.



### Normal

To do a *foreach* loop, the syntax is `foreach ($collection as $item){}`. The use of the *as* is keyword and functions as the : for the C++ way. The collection will be the thing that will be iterated over and the item will be the particular item for that particular index iteration. This is good if only need to use the value and not change the value at all.

```php
$collection = array("Gabriel", "Centeno", 6);

foreach ($collection as $item){
    if ($item === "Centeno"){
        echo "<p>name found</p>";
    } else{
        echo "<p>name not found</p>";
    }
}
```



### Associative

This way is useful when wanting to get the value and modify that value. The syntax for this is `foreach ($collection as $key => $value)` where:

- The $collection is the collection of items
- The $key is a copy of the index for that position
- The $value is a copy of the item for that index position



```php
<?php
$user = [
    "name" => "Alice",
    "city" => "London",
    "age" => 30
];

foreach ($user as $property => $data) {
    echo $property . " is " . $data . ".\n";
}
```

> [!IMPORTANT]
>
> Can use this to also modify the values in the array by using the $key



### Advanced

When it comes to the previous version of the *foreach* loop for normal arrays, there is a way to change the value, but this requires a special syntax. Now do `foreach ($collection as &$item)`. The difference here is adding the & in front of the item; this will now return the original copy of the item for that index and not a copy of it. This works since now the $item will be a direct alias to the memory location to that index position.



> [!CAUTION]
>
> Unlike the normal version, the $item variable will stay active even once out of the *foreach* loop. So this variable will hold the memory location to the last index of that collection. This means the use of the **unset()** function is needed here and the alias variable needs to be passed to it.

```php
<?php
$numbers = [1, 2, 3];

foreach ($numbers as &$value) { // Note the ampersand &
    $value *= 2; // Directly modifies $numbers[current_index]
}
unset($value); 
// This breaks the reference $value holds to the last array element 
// If omited this, $value remains an alias to $numbers[2], which can cause bugs.
?>
```

