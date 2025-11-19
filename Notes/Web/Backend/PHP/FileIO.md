# File IO

When wanting to work with file, there is a special way to do this using special functions. The first important function is the **fopen()**; this will return a *resoure type* or false if failed. This takes at least two arguments:

1. Path to file name
2. The mode to open the file in
3. The specific path to search. This will be true or false



### File modes available

- r --> read only mode and pointer starts at beginning
- r+ --> read and write mode and pointer starts at beginning
- w --> write only and create the file it is does not exist or deletes all content if it does exist. Pointer starts at beginning.
- w+ --> read and write mode. Will create the file if it exists or delete all  content if it does exit. Pointer starts at beginning.
- a --> opens for write only, but pointer does not start at beginning and    instead is located at the end.
- a+ --> opens for write and read only, but pointer does not start at beginning and instead is located at the end.
- x --> This is a more strict version of 'w' mode. This will create a file and open it in write mode, but if the file already exist then it will throw an error of type *E_WARNING*. This is best to use when wanting to make sure that a files content is never truncated. The pointer is at the start of the file.
- c --> This will open a file or create it in write mode. However, if the file does exist, it will not truncate (delete content) from the file, but still put the pointer at the beginning of the file. So when writing to the file it will then write over that data.

> [!NOTE]
>
> If wanting to work with binary files, for all of these options just add the letter "b" to right after the letter like "rb+" or "wb"



Once done with a file resourse it should be closed so make sure to close it with the **fclose()** and this will only take one argument of a file type. This will return true if it was closed and false if not.



## File existance

When it comes to opening a file, it is best to check if it even exist first. The way to check if it exist is using the function **file_exists()**. This takes a string of the file name or file path. This will return true if it exist and false if it does not.

> [!NOTE]
>
> Can also pass in a directory and this can check that too



To specifically check if the item is a file and it exist use the **is_file()**. This will check if the item exsit AND if it is a file. If it is then return true and otherwise return false. This takes one parameter and that is the string name of the file.



To check if a file or directory exist AND if the correct permissions are set to be able to read its contents, use the **is_readable()**. This will just take a string name of the file/directory and will return true if it is readable and exist or  return false if the item is not readable or does not exist.



To check if a file or directory exist AND if the file permissions to write to it is set; use the **is_writable()** to check this. This take a string of the file/directory name or path. Returns true if it is and false if it is not.



## Reading content

Once a file it opened, it can be read from (if read mode is set). To read from a file use the **fread()**. This will return a string of all the contents read or false if it fails to read. This takes two arguments:

1. The name of the 
2. The maximum number of bytes to read

> [!TIP]
>
> To read all the content at once from the file just use **filesize()** and pass in the file made resource from **fopen()**. The **filesize()** returns an int for the total size, in bytes, of the file or false if it does not exist or lacks read permission 

The **fread()** function stops reading the file once the **$length** number of bytes has been read or the end of file (*EOF*) has been reached.



To manually check if a file is at *EOF*, use the **feof()**. This takes on parameter of the resource made from **fopen()**. Returns true if it is and false otherwise.



To read a file line by line instead of all the contents at once like **fread()** does, use the **fgets()** function. This takes two parameters:

1. File resource made by **fopen()**.
2. The length of bytes to read from that line. This is an optional parameter. If it is not set then this will always read to the end of the string. This returns the string read (including the newline character) if everything is all good and not at *EOF*, but this returns false if at *EOF* or some error occured.



If wanting to just use all the text read and paste it into HTML, use the **nl2bl()** function. This function converts all newline characters into HTML compatable  `<br>`. If this passes it returns the new string made for HTML. This will take two parameters:

1. The string; hopefully the string gotten from **fread()** or **fgets()**.
2. This optional, but this can be set to false and it will use XML break tags instead of HTML style ones.





## Best way to read file

When it comes to the best way to read a file, this is using the **file_get_content()** function. If this passes it will return a string of all the file content read or false if it fails. This function takes many parameters:

1. Name of the file, as a string, to read from and this is required
2. This can be true or false. If this is true then it wont just look in the current directory, but also other directories specified for the file. These directories are specififed in a file called `php.ini`, but this file is not one made manually and should be created when installing the PHP on the server. Pretty much just have this be false.
3. This is something, but just set it to false. This is an optional parameter.
4. Offset where the function starts reading on the original stream. If it is  negative, the offset counts from the end of the stream. This is optional and if left empty then reads from beginning of the file.
5. Specify the maximum length of data to read. By default, the function reads data till the end of the file. This is an optional parameter.



Each of these parameters are named respectfully: 

- $filename 
- $use_include_path
- $context
- $offset
- $maxlen

> [!NOTE]
>
> Can just used named parameters when calling the function like $offset = 30 to avoid having to set the values for the `$context` and `$use_include_path`.
>
> For example **file_get_content("yes.txt", \$offset=30, \$maxlen=512)**



## File creation

There are two ways to create a file:

- Using the **fopen()** with the certain modes set like 'x', 'w', or 'c'.
- Using the **file_put_contents()**. This takes the following arguments
  1. $filename --> string of the file to open or create in write mode.
  2. $data --> This is the data to write to the file.
  3. $flags --> This 
  4. $content --> That advanced thing to just leave alone.

> [!IMPORTANT]
>
> For **file_put_contents()** the first two parameters are required, but the others are optional.



> [!NOTE]
>
> The FLAG values are:
>
> - LOCK_EX --> Acquires an *exclusive lock* on the file during the write     operation. This prevents other scripts/processes from reading or writing to the file simultaneously, safeguarding data integrity during concurrent access.
> - FILE_APPEND --> If the file already exists, the new data is appended to the end instead of overwriting the existing content.
> - FILE_USE_INCLUDE_PATH --> If set, PHP will search for the file in the directories specified by the *include_path* configuration setting. This is less common for writing than for reading.
>
> All three of these are really just integers.
>
> To have more than one of these set at once seperate them with |
>
> Remember that constants do not require $ when being used.



## Writing to a file

When writing to a file, this can be done with two ways:

- **fputs()** --> This is used to write content to the file. This will take only three parametets:
  1. File handler resource made by **fopen()**
  2. String data to write
  3. Max number of bytes to write. This is the only optional field
- **file_put_content()** --> This is the same function mentioned before



## Creating a temp file

A temporary file is one that will be created and ONLY exist until:

- Calling the `fclose()` function.
- When the file handle doesn’t have any references.
- When the script ends.



There are two ways to create a temporay file:

- **tmpfile()** --> This creates a temporary file in the current directory in w+ mode. This returns the file handle to this resource or returns false if it was not made. This only takes one parameter and that is the name of the file in a string.

- **tmpnam()** --> 



## Downloading a file

This can be done with the **readfile()**. This function will read data from a file and write it to the output stream buffer (web browser) right away. This makes is extreamly efficient since there is no need to store the returned string value in a variable unlike the **file_get_contents()**.

This takes three parameters, but only the first is needed and will ever be used; that is the path of the file to read from in a string. If this succeeds then it will return an int on how many bytes were read from the data file, but if it failes then return false.

When using **readfile()** on something like an image, video, etc, since this content is just placed into the output stream buffer (web browser) right away, if it anything besides normal text, the used of the **header()** will need to be used. This is used to add the header content to something like a packet.



> [!CAUTION]
>
> When reading something that is not normal text (image, media, etc) using the **readfile()** function, this file cannot have ANY other content being written to the browser or else this could cause a corruption of the data and make it so it will not download correctly. To have this there with other HTML code use 



