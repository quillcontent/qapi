# Errors

> ### HTTP response codes
Quill uses standard HTTP response codes to indicate the success or failure of an API request. In general, codes in the 2xx range indicate success. Codes in the 4xx range indicate an error that failed given the information provided (e.g., a required parameter was missing, an API key was missing/expired, etc.). Codes in the 5xx range indicate an error with Quill's servers (these are rare).

> ### Handling errors
Our API can raise exceptions for many reasons, such as an invalid auth token charge, invalid parameters, authentication errors, and network unavailability. We recommend writing code that gracefully handles all possible API exceptions.

### The Quill Platform API uses the following HTTP response error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request 
401 | Unauthorized 
403 | Forbidden
404 | Not Found 
405 | Method Not Allowed
406 | Not Acceptable
429 | Too Many Requests
500 | Internal Server Error
503 | Service Unavailable
