# Try-Catch 

When wanting to test with some possible dangerous code that could result in a fatal error, it is best to use a *try-catch* block. This is a way to catch fatal errors and handle them gracefully rather than have them crash the code.



To use this make two separate blocks like:

```php
try{
    //code here
} catch(){
    // code here
}
```

The *try* block does not take any arguments as this is just gonna be the area where code is tested so nothing is passed to this. However, for the **catch()** portion, this could or could not need a parameter. If the code were to throw an error ONLY THEN will the **catch()** block will go off, otherwise if all is good then the **catch()** will never excute.



The argument the **catch()** will take is a type from the built in object  