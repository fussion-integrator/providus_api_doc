# Error Handling

Our API communicates errors through standard HTTP status codes and provides detailed error messages in the response body. Here are common HTTP status codes and their meanings:

### 

[](#common-http-status-codes)

Common HTTP Status Codes

*   **200 OK:** The request was successful.
    
*   **400 Bad Request:** The request was malformed or invalid.
    
*   **401 Unauthorized:** Authentication failed or missing credentials.
    
*   **404 Not Found:** The requested resource was not found.
    
*   **429 Too Many Requests:** Exceeded rate limits.
    

### 

[](#handling-errors)

Handling Errors

When an error occurs, the API response includes a JSON object with an `error` field containing the error message. Example:

Copy

```
{
  "error": "Invalid API key. Please provide a valid key."
}
```

[PreviousOAuth 2.0 Authentication](/reference/api-reference/oauth-2.0-authentication)[NextData Formats](/reference/api-reference/data-formats)

Last updated 1 year ago