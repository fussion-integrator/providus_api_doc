# Data Formats

Our API supports multiple data formats for both request payloads and response bodies. Here are the primary formats:

### 

[](#id-1.-json-default)

1\. JSON (Default)

*   **Request:** Ensure your request payload is in valid JSON format.
    
*   **Response:** All responses are in JSON format by default.
    

Example Request:

Copy

```
{
  "key1": "value1",
  "key2": "value2"
}
```

### 

[](#id-2.-form-data)

2\. Form-Data

For certain endpoints, you may need to send data using the `application/x-www-form-urlencoded` format.

Example Request:

Copy

```
httpCopy codePOST /endpoint
Content-Type: application/x-www-form-urlencoded

key1=value1&key2=value2
```

### 

[](#id-3.-file-uploads)

3\. File Uploads

If your application requires file uploads, use the `multipart/form-data` format.

Example Request:

Copy

```
httpCopy codePOST /upload
Content-Type: multipart/form-data

file=@/path/to/file.txt
```

Make sure to check the documentation for each endpoint to determine the required data format.

### 

[](#id-4.-pagination)

4\. Pagination

For resource-intensive endpoints that return large sets of data, our API supports pagination. This allows you to retrieve a subset of data in each request.

### 

[](#query-parameters)

Query Parameters

*   `**page**`**:** Specifies the page number (e.g., `page=1`, `page=2`).
    
*   `**per_page**`**:** Specifies the number of items per page (e.g., `per_page=10`).
    

### 

[](#example-request)

Example Request

Copy

```
GET /large-data-endpoint?page=2&per_page=20
```

### 

[](#example-response)

Example Response

Copy

```
jsonCopy code{
  "data": [
    // ...items for page 2
  ],
  "meta": {
    "page": 2,
    "per_page": 20,
    "total_items": 100
  }
}
```

[PreviousError Handling](/reference/api-reference/error-handling)[NextSandbox](/reference/sandbox)

Last updated 1 year ago