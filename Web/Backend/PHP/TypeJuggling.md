# Type Juggling

When comparing two values, just like in JavaScript, there are two ways to do this with the == or ===.



When using the ==, this will convert the one of the two values into a common type so they can be compared. For example, doing `20 == "20"` will result in a true since this will auto convert the string to an int. This also works for things like operator operations (+, -, *, etc). For example, `100 + "20"` will result in integer 120. This is basically a lose type of equality.



When using the ===, this is a stronger form of equality. This will compare to see if the value and data type are the same just like in JavaScript.



