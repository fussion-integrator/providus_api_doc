1. Reference
2. API Reference

# Data Formats

Our API supports multiple data formats for both request payloads and response bodies. Here are the primary formats:

### 1. JSON (Default)

- Request: Ensure your request payload is in valid JSON format.
- Response: All responses are in JSON format by default.

Request: Ensure your request payload is in valid JSON format.

**Request:**Response: All responses are in JSON format by default.

**Response:**Example Request:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "key1": "value1",
  "key2": "value2"
}
```

### 2. Form-Data

`application/x-www-form-urlencoded`Example Request:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
httpCopy codePOST /endpoint
Content-Type: application/x-www-form-urlencoded

key1=value1&key2=value2
```

### 3. File Uploads

`multipart/form-data`Example Request:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
httpCopy codePOST /upload
Content-Type: multipart/form-data

file=@/path/to/file.txt
```

Make sure to check the documentation for each endpoint to determine the required data format.

### 4. Pagination

For resource-intensive endpoints that return large sets of data, our API supports pagination. This allows you to retrieve a subset of data in each request.

### Query Parameters

- page: Specifies the page number (e.g., page=1, page=2).
- per_page: Specifies the number of items per page (e.g., per_page=10).

`page`**:**`page=1``page=2``per_page`**:**`per_page=10`### Example Request

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
GET /large-data-endpoint?page=2&per_page=20
```

### Example Response

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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