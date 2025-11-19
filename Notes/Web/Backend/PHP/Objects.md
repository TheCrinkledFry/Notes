# Objects

When it comes to working with OOP in PHP, it is good to know:

- When to use OOP
- How to do OOP
- Why use OOP



> [!TIP]
>
> When creating this object class, it is good practice to put it in a separate file and in something like the index.php file use the require_once thing and include the class php file made. 



## How to make objects

When making an object and it is in a separate file, it is convention to have the file start with a capital letter like Car.php and have the actual object name with the same as the file name



To create use the *class* keyword followed by the class name, which by convention should be the same as the file name. After the file name put a set of curly braces.



Remember objects have properties(variables) and methods(functions).

### Properties

When creating properties for a class, have to use something called *visibility modifiers*. This will affect the scope of who has access to the properties. The *visibility modifiers*  would go BEFORE the name of the property. The *visibility modifiers* are:

- private --> Only that object itself has access to that property/method
- public --> Anyone has access to that property/method
- protected --> This make it so if another class that inherits this class can still have access to the propert(ies/y)/method(s).

> [!NOTE]
>
> The *visibility modifiers* are like Java's private, public, etc.

> [!NOTE]
>
> When creating a property this should go towards the top of the class.



If the property has a value assigned then all instances of that object will have that value premade, so it is best to not set the variable to anything (not even null).



```php
<?php
class Car{
    private $brand;
    protected $color;
    public $cost;
    
    public function __construct($cost){
		this->$cost = $cost;
    }
}
```



### Construct and Destruct

When it comes to methods (functions) the most important one is called the *constructor*. This is the default method that is used to actually create the instance of the object. This function will have a special name of **__construct()** and this should always have a *visibility modifier* of public.



Now the parameters of the **__construct()** should only be properties made for that object that should be assigned some value when the object is created.



The opposite of **__construct()** is **__destruct()**. This function is automatically called once the object is destroyed (no reference to it) or the script ends. This function will not be able to take any parameters. This is where all resource clean up should be done like closing files, connections, etc.



```php
<?php

class Car{
  private $brand;
  protected $color;
  public $cost;

  public function __construct($brand, $color, $cost){
    $this->brand = $brand;
    $this->color = $color;
    $this->cost = $cost;
  }
  public function __deconstructor(){
    echo "<p>This was a smart move to end now</p>";
  }
}
```



### Methods

When it comes to *visibility modifiers* for methods, each methods needs one too. This would go BEFORE the keyword *function*. 



When creating any other method for that object then declare a function like normal giving its own name, but remember still need to give it a *visibility modifier* as well before the *function* keyword.



When it comes to dealing and assigning an object its values, need to use the *$this* keyword. Under the hood it signals that the object instances calling the method needs to be changed. When it comes to accessing the properties/methods of an object, use ->

> [!IMPORTANT]
>
> When accessing a property of an object, the property the arrow points to does not need the dollar sign in front of it.



```php
<?php

class Car{
  private $brand;
  protected $color;
  public $cost;

  public function __construct($brand, $color, $cost){
    $this->brand = $brand;
    $this->color = $color;
    $this->cost = $cost;
  }
  public function getBrand(){
      return $this->brand;
  }
}
```

### Creating object instance

When it comes to creating an instance of the object, have to use the *new* keyword and then right after type the name of the object, but call it like a function. This will then call the **__construct()** function by default.

```php
<?php

class Car{
  private $brand;
  protected $color;
  public $cost;

  public function __construct($brand, $color, $cost){
    $this->brand = $brand;
    $this->color = $color;
    $this->cost = $cost;
  }
}

$car = new Car("BMW", "Blue", 40_000);
echo $car->cost;
print_r($car);
```

> [!TIP]
>
> The way currently set up requires that three values be given. However, to make it so optionally values can be given:
>
> - Do not make that parameter part of the function constructor
> - Give that parameter a default value in the function part
> - Function overloading



### Inheritance

When it comes to having a class inherit things from another class, use the *extends* keyword right AFTER the name for the new object is given and then create class like normal.

> [!IMPORTANT]
>
> All new classes that *extend* another class get access to all their properties that have a *visibility modifier* of protected or public.



New new class made that *extends* another class can its own custom methods/properties to itself to get extended functionality. The class that inherits the previous class is called a *child class* and the class that is part of that new class is called the *parent class*.



> [!CAUTION]
>
> When working with objects that are child class, have to always include the original parent file (or however made) BEFORE creating or including the object that is a child object of it



When a *child class* make a new method, if that method is the same name as a method in the *parent class*, then this will override the *parent class* version and the *child class* will no longer have access to it. To make it so the child class can have a method with the same name AND still have access to the parent version, put *parent::* BEFORE function being called that should be from the parent. For example if the child and parent class had a function called connect(). The child would `connect();` anywhere in that objects methods, but to get the version of the parent do `parent::connect();`.



## Traits classes



## Interfaces classes



## Abstract classes



## Final classes

