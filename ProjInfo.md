# Project Information



- The sixth bullet point will be "I need the ability to write reports"

- Documents to upload will be PDF documents ALWAYS, however still error check for other types. These are all scanned pdf documents about loan information

- When it comes to the information that needs to be seen in the report, they need to see:
  
  1. Show all complete loans (loans that have all 8 needed documents)
  
  2. Incomplete loans (missing at least one document) and what are the documents missing for that loan.
  
  3. Show all incomplete loans
  
  4. How many documents does a loan have?
  
  5. How many copies of the same document for a loan are there
  
  6. Which documents are missing from a particular loan
  
  7. Show all loans that are missing a particular document
  
  8. What is the most common missing document
  
  9. sort by document size
  
  10. Search how many of a particular document there is across all loans
  
  11. Search by loan ID and particular document
  
  12. What was the query made by the user, what document was looked up, when was the loan ID looked up, what loan ID was looked up, and at what time and date it was done.
  
  13. total number of loans on the system
  
  14. Search how many time a document has been accessed (like downloaded or something) and not just queried.

- The document needed for a loan to be complete are: credit document,   closing document, title document, financial document, personal document, legal document, MOU document, and disclosure document.

- The documents will be read only so cannot edit them and if wanting to change them, must upload new version of it.

- Since there can be multiple versions of the same document associated with the same loan, must have a way to track the most current version of the loan while still keeping track of all previous versions.

- Loan ID is unique

- Need to have ability to check if anyone ever viewed the document

- A loan is considered complete if it at least has one copy of all the needed 8 documents.

- Track what document was queried by the user

- This system will only ever have one user and that is the web user

- Track if the loan number is correct when adding document to loan

- Have way to fix that if a document that was sent to loan B, but was supposed to be part of loan A, is some how auto fixed to move to the correct one.

- All documents should ALWAYS be labeled, but should still check to make sure that is the case
  
  

Crontab -e --> edit current users crontab

Crontab -l --> List current users crontab

> This is a small test

> [!NOTE]
> 
> The Cron tab will execute sequentially
> 
> The Cron does not have any environment variables and does not know any paths to anything in the system so it all needs to be specified like where is the php thing
> 
> /usr/bin/php
> 
> sudo su --> will bring to the root user so can mess with cron tab



> [!IMPORTANT]
> 
> To check PHP errors on the system do `cat /var/log/nginx/error.log`



Payload will come in as session ID if all good when creating session



When it comes to making the curl request, is there a way to tract how long the actual request took?



There is random white noise built to randomly disconnect, so must have a way to reconnect or something. This should also be logged. Important thing to know is this can happen at any part of the system.



Must log all times I connect and disconnect to something



How to deal with a long delay which is caused by a timeout



Always make sure to close session once done with everything



session id could be killed randomly at any point of time



log execution time



log which call is being made and will log error, but if successful then just tell the call that was successful



Once the session id is gotton successfully, create a constant variable for it so it does not change



When trying to first create session, if it is not able to because a previous one exist, then we need to clear the session then and then try to create one again.



### Data format to pass

- When calling the clear_session it is -->                                                  `"username=" . USERNAME . "&password=" . PASSWORD;`
- When calling the create_session it is -->                                                `"username=" . USERNAME . "&password=" . PASSWORD;`
<<<<<<< HEAD
- When calling the close_session it is --> `"sid=$sid"`
- When calling the query_files it is -->                                                      `$Data = "uid=" . USERNAME . "&sid=$sid";`
- When calling the request_file it is --> `$Data = `
  
  

=======
- When calling the close_session it is --> `"sid=$Sid"`
- When calling the query_files it is -->                                                      `$Data = "uid=" . USERNAME . "&sid=$Sid";`
- When calling the request_file it is --> `$Data = "sid=$Sid"`


>>>>>>> e447b602f91d9a31e3ea34cddf8c28fe54a79e20

#### Previous session exist when trying to connect

```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: Previous Session Found
    [2] => Action: Must clear session first
)
```

#### New connection made

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: Session Created
    [2] => 26b988b9f267068ff8752eb27f824ef7bde6d484 // example payload will always be 40 or could be null (aka no data)
)
```

#### Sucessful clearing of session

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: Previous Session Found
    [2] => Action: Session Cleared
)
```

#### Failure of clearing session

```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: No previous session found
    [2] => Action: Create session first
)
```

#### Success of closing session

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: SID closed successfully
    [2] => Action: Done
)
```

#### Failure of closing session

```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: No previous session found
    [2] => Action: Create session first
)
```

#### Incorrect endpoint reached

```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: Invalid/Disabled Endpoint
    [2] => Action: Please try again
)
```

#### Failure to query files

```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: SID/UID Missing
    [2] => Action: Please try again
)
```

#### No new files found in query files

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: No new files found
    [2] => Action: None
)
```

#### Sucess to query files example

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: ["487932100-Tax_Returns-20251101_21_26_55.pdf","487932100-MOU-20251101_21_26_55.pdf","487932100-Internal_1-20251101_21_26_55.pdf","487932100-Closing-20251101_21_26_55.pdf","487932100-Title_2-20251101_21_26_55.pdf","487932100-Internal-20251101_21_26_55.pdf","487932100-Credit-20251101_21_26_55.pdf","487932100-Title-20251101_21_26_55.pdf","613490078-Tax_Returns_1-20251101_21_27_05.pdf","613490078-Internal_4-20251101_21_27_05.pdf","613490078-Financial-20251101_21_27_05.pdf","613490078-Tax_Returns_3-20251101_21_27_05.pdf","613490078-MOU-20251101_21_27_05.pdf","613490078-Tax_Returns_2-20251101_21_27_05.pdf","613490078-Tax_Returns-20251101_21_27_05.pdf","613490078-MOU_5-20251101_21_27_05.pdf","613490078-Internal-20251101_21_27_05.pdf","014987236-Internal-20251101_21_27_18.pdf","014987236-Title-20251101_21_27_18.pdf","014987236-Internal_1-20251101_21_27_18.pdf","014987236-MOU-20251101_21_27_18.pdf","014987236-Closing-20251101_21_27_18.pdf","739421800-Financial-20251101_21_27_31.pdf","739421800-MOU-20251101_21_27_31.pdf","739421800-Financial_3-20251101_21_27_31.pdf","739421800-Financial_1-20251101_21_27_31.pdf","739421800-Closing-20251101_21_27_31.pdf","739421800-Internal-20251101_21_27_31.pdf","739421800-Closing_4-20251101_21_27_31.pdf","739421800-MOU_5-20251101_21_27_31.pdf","739421800-Title-20251101_21_27_31.pdf","739421800-Closing_2-20251101_21_27_31.pdf"]
    [2] => Action: Continue
)
```

#### Query files success but nothing returned

```pseudocode
Array
(
    [0] => Status: OK
    [1] => MSG: []
    [2] => Action: Continue
)
```

Error when making file request

```pseudocode
["Status: ERROR","MSG: file id can not be NULL","Action: Please try again"]
```

#### Error when making file request with bad Sid

<<<<<<< HEAD
```php
<?php

$x = 50;

for (;$x < 100; $x++)
    echo $x;
?>
```
=======
```pseudocode
Array
(
    [0] => Status: ERROR
    [1] => MSG: SID not found
    [2] => Action: Please try again.
)
```



#### Error when making a file request with bad file name

```pseudocode
["Status: ERROR","MSG: file id can not be NULL","Action: Please try again"]
```



#### Error when making request with bad sid and file name

```pseudocode
["Status: ERROR","MSG: SID\/UID Missing","Action: Please try again"]
```



When parsing the file name, it is seperated by `-`. The parts are:

1. Loan number
2. Document type
3. Timestamp --> YEARMONTHDAY_HOUR_MINUTE_SECOND
4. Ending part is file extension like seperated with .pdf and not -

#### EXAMPLE FILE NAMES

- 913004768-Closing-20251103_07_45_12.pdf
- 913004768-Financial_3-20251103_07_45_12.pdf
- 402981763-Internal-20251103_07_45_12.pdf
- 781243960-Financial_1-20251103_07_45_12.pdf



```php
<?php
  $db = new mysqli("localhost", "WebUser", PASSWORD, "file_storage");
  $hold = explode("-", $file);
```





54 235 589
