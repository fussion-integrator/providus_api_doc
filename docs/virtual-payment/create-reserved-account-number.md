# Create Reserved Account Number

Create a reserved virtual account number for permanent use.

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method post">POST</div> `/api/v1/virtual/reserved`

## Request Body

```json
{
  "customerName": "John Doe",
  "customerEmail": "john@example.com"
}
```


## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "data": {
    "accountNumber": "9876543210",
    "accountName": "John Doe"
  }
}
```


## Sample Implementation

```curl
curl -X POST "https://api.providusbank.com/api/v1/virtual/reserved" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "customerName": "John Doe",
  "customerEmail": "john@example.com"
}'
```

```python
import requests

url = "https://api.providusbank.com/api/v1/virtual/reserved"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

data = {
  "customerName": "John Doe",
  "customerEmail": "john@example.com"
}
response = requests.post(url, headers=headers, json=data)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/virtual/reserved', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
  "customerName": "John Doe",
  "customerEmail": "john@example.com"
})
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "https://api.providusbank.com/api/v1/virtual/reserved";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$data = json_encode({
  \"customerName\": \"John Doe\",
  \"customerEmail\": \"john@example.com\"
});
$context = stream_context_create([
    'http' => [
        'method' => 'POST',
        'header' => implode("\r\n", $headers),
        'content' => $data
    ]
]);

$response = file_get_contents($url, false, $context);
echo $response;
?>
```

```java
import java.net.http.*;
import java.net.URI;

HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://api.providusbank.com/api/v1/virtual/reserved"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .POST(HttpRequest.BodyPublishers.ofString("{\"customerName\":\"John Doe\",\"customerEmail\":\"john@example.com\"}"))
    .build();

HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());
System.out.println(response.body());
```

```csharp
using System;
using System.Net.Http;
using System.Text;

var client = new HttpClient();
client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_API_KEY");

var json = @"{
  "customerName": "John Doe",
  "customerEmail": "john@example.com"
}";
var content = new StringContent(json, Encoding.UTF8, "application/json");
var response = await client.PostAsync("https://api.providusbank.com/api/v1/virtual/reserved", content);

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```

