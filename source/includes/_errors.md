# Errors

<aside class="notice">Quill uses standard HTTP response codes to indicate the success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that failed given the information provided (e.g., a required parameter was missing, an API key was missing/expired, etc.), and codes in the 5xx range indicate an error with Quill's servers (these are rare).</aside>

The Quill Platform API uses the following error codes:


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
