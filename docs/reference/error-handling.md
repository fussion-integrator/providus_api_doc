1. Reference
2. API Reference

# Error Handling

Our API communicates errors through standard HTTP status codes and provides detailed error messages in the response body. Here are common HTTP status codes and their meanings:

### Common HTTP Status Codes

- 200 OK: The request was successful.
- 400 Bad Request: The request was malformed or invalid.
- 401 Unauthorized: Authentication failed or missing credentials.
- 404 Not Found: The requested resource was not found.
- 429 Too Many Requests: Exceeded rate limits.

200 OK: The request was successful.

**200 OK:**400 Bad Request: The request was malformed or invalid.

**400 Bad Request:**401 Unauthorized: Authentication failed or missing credentials.

**401 Unauthorized:**404 Not Found: The requested resource was not found.

**404 Not Found:**429 Too Many Requests: Exceeded rate limits.

**429 Too Many Requests:**### Handling Errors

`error````inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "error": "Invalid API key. Please provide a valid key."
}
```

Last updated 1 year ago