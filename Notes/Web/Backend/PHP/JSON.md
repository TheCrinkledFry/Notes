# JSON

When it comes to dealing with or wanting to deal with json data, there is a way to do this.

- Turn the data into JSON
- Convert JSON into an object or associative array



There are two functions to do each of these:

1. **json_encode()** --> Takes one parameter, typically an associative array, and returns a JSON-encoded string if successful, or false if encoding fails.

2. **json_decode()** --> Takes four parameters max. The first is of type string with the string being in a string format. The second is a boolean value for how the return data should be encoded, false for retuns PHP object and true retuns associative array; by default this is set to false. The third and fourth are not really needed to be worried about and just leave them as is.



If an error occurred when trying to convert from/to JSON, there could be a possible error. There is a specific way to check if an error occurs with this by using the **json_last_error()** and **json_last_error_message()**.

- **json_last_error() **--> This will return a constant that represents and error code. The possible constants to use are:

| Constant                      | Meaning                            |
| ----------------------------- | ---------------------------------- |
| `JSON_ERROR_NONE`             | No error occurred                  |
| `JSON_ERROR_DEPTH`            | Maximum stack depth exceeded       |
| `JSON_ERROR_STATE_MISMATCH`   | Invalid or malformed JSON          |
| `JSON_ERROR_CTRL_CHAR`        | Unexpected control character found |
| `JSON_ERROR_SYNTAX`           | Syntax error                       |
| `JSON_ERROR_UTF8`             | Malformed UTF-8 characters         |
| `JSON_ERROR_RECURSION`        | Recursive references detected      |
| `JSON_ERROR_INF_OR_NAN`       | `INF` or `NaN` values in data      |
| `JSON_ERROR_UNSUPPORTED_TYPE` | Type not supported for encoding    |

- **json_last_error_message()** --> This is just used to print a human readable description string of the error that occured.

> [!TIP]
>
> A good thing to do is test against the `JSON_ERROR_NONE` with                     `json_last_error()` with something like `!==` so if it is not equal to             `JSON_ERROR_NONE` then something bad happened.

