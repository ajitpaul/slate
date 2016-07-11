# Errors


Our API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is bad
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- requested is hidden for administrators only
404 | Not Found -- The specified item could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
429 | Too Many Requests -- You're requesting too many things Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
