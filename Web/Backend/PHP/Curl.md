# CURL

*CURL* is a way in PHP to make requests from things like APIs or just        communicating with other servers. The most common protocol to be used with this is HTTP/HTTPS.



The PHP *cURL extension* (`curl_*` functions) acts as a wrapper around this   library, allowing PHP scripts to perform robust network requests for tasks like interacting with APIs, logging into websites, or downloading files.



Here are the common steps that would be taken to execute a curl request:

| Step          | Function                                   | Purpose                                                      |
| ------------- | ------------------------------------------ | ------------------------------------------------------------ |
| 1. Initialize | `curl_init()`                              | Creates a new cURL session and returns a resource handle (like a pointer to the session). |
| 2. Configure  | `curl_setopt()` or   `curl_setopt_array()` | Sets all the parameters and instructions for the request (URL, headers, method, timeouts, etc.). |
| 3. Execute    | `curl_exec()`                              | Executes the transfer with the configured options, sending the request and receiving the response. |
| 4. Close      | `curl_close()`                             | Closes the session and frees up the memory and system resources associated with the handle. |



### Syntax for the functions

- **curl_init(OptionalString)** --> this can take one optional string value and that will be for setting the URL for the curl object
- **curl_setopt(resource \$ch, int \$option, mixed \$value): bool**
  	1. This is required and it is the made curl object from **curl_init()**
  	1. The is required and it is the option that will be added to the curl object
  	1. This is required and it is the respected value for the selected option
- **curl_exec(curl resource)** --> Returns true or false and right away displays content to the screen like **readfile()**. However, will return a string of the  response if the option *CURLOPT_RETURNTRANSFER* was set
  1. This is the curl resource made from **curl_init()**
- **curl_close()**
  1. Takes the curl object to close resource to



The **curl_init()** is what is needed to first create a curl resource object. This is what will be returned to the variable and should be the first thing done.

> [!TIP]
>
> Can pass in the string URL that this will be making request to in the **curl_init()** function, and this would prevent the need to needing call the **curl_setopt()** and set it that way. However, it can be done also with an   option.



[click here](https://www.php.net/manual/en/curl.constants.php#constant.curlopt-abstract-unix-socket) to see all the options this can be set to

Common options here

| Basic Request & Response Handling | Description & Value Type                                     |
| --------------------------------- | ------------------------------------------------------------ |
| CURLOPT_URL                       | This is used to set the URL for the curl handle object if it was not set when **curl_intit()** was called. The data for this will be a string of the URL |
| CURLOPT_RETURNTRANSFER            | Tells `curl_exec()` to return the transfer as a string instead of outputting it directly. The data for this will be a boolean of true. |
| CURLOPT_TIMEOUT                   | The maximum number of seconds to allow cURL functions to execute. The data for this will be an integer |
| CURLOPT_CONNECTTIMEOUT            | The maximum number of seconds to wait while trying to connect. The data for this will be an integer |
| CURLOPT_FOLLOWLOCATION            | Tells cURL to follow any `Location:` header that the server sends (HTTP redirects). The data for this will be a boolean of true |



| POST/PUT/Custom Requests OPTIONS | Description & Value Type                                     |
| -------------------------------- | ------------------------------------------------------------ |
| CURLOPT_POST                     | Sets the request method to POST. The data value for this will be a boolean of true |
| CURLOPT_POSTFIELDS               | The data to send in an HTTP POST operation. For a string, it should be URL-encoded. For an array, cURL automatically encodes it as `multipart/form-data`. The data can be a string or array, but using an array will be easier because it will do some conversion already. |
| CURLOPT_CUSTOMREQUEST            | Used to set a custom request method PUT, DELETE, OPTIONS. The data value for this will be a string of the type of method. |



| Headers & Authentication | Description & Value Type                                     |
| ------------------------ | ------------------------------------------------------------ |
| CURLOPT_HTTPHEADER       | An array of HTTP header fields to set, formatted as  "Header-Name: Value". Essential for setting "Content-Type", authorization tokens, etc. The data value for this will be an array of strings. |
| CURLOPT_USERPWD          | Passes a username and password for basic HTTP authentication. Used in conjunction with CURLOPT_HTTPAUTH. The data value for this is a string with the format `username:password` |
| CURLOPT_HTTPAUTH         | The HTTP authentication method to use (e.g.,CURLAUTH_BASIC, CURLAUTH_DIGEST). The data value for this will be |

