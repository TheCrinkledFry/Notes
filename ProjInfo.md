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

- The document needed for a loan to be complete are: credit document, closing document, title document, financial document, personal document, legal document, MOU document, and disclosure document.

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



Payload will come in as session ID



There is random white noise built to randomly disconnect, so must have a way to reconnect or something. This should also be logged. Important thing to know is this can happen at any part of the system. For example another can be the session not being closed when we thought it did.



Must log all times I connect and disconnect to something



How to deal with a long delay which is caused by a timeout



Always make sure to close session once done with everything





## States for success connection response

When it comes to creating a session, this comes from going to the URL `https://cs4743.professorvaladez.com/api/create_session`

### Success Response

Status will be --> OK

### MSG states

- Session Created

### Last part

- Payload data for session id, which will always be unique



## Error in creating session

### Status

- ERROR



### MSG

- Invalid credentials
- Previous Session Found



### Action

- This will have the format: Action: Must clear session first

## Clearing the session

This involves using the ULR of `https://cs4743.professorvaladez.com/api/clear_session` to have this done.



## Clearing success

### Status

- OK



### MSG

- Previous Session Found



### Action

- Session cleared



## Session clear fail

### Status

- ERROR

### MSG

- No previous session found

### Action

- Create session first