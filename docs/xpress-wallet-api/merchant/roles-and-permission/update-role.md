# Update Role

Update an existing role's name and permissions.

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method put">PUT</div> `/api/v1/wallet/merchant`



## Request Body

```json
{
  "reference": "REF123456789"
}
```


## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "message": "Operation completed successfully",
  "data": {
    "result": "success"
  }
}
```

## Sample Implementation

```curl
curl -X PUT "https://api.providusbank.com/api/v1/wallet/merchant" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "reference": "REF123456789"
}'
```

```python
import requests

url = "https://api.providusbank.com/api/v1/wallet/merchant"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

data = {
  "reference": "REF123456789"
}
response = requests.put(url, headers=headers, json=data)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/wallet/merchant', {
  method: 'PUT',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
  "reference": "REF123456789"
})
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "https://api.providusbank.com/api/v1/wallet/merchant";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$data = json_encode({
  \"reference\": \"REF123456789\"
});
$context = stream_context_create([
    'http' => [
        'method' => 'PUT',
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
    .uri(URI.create("https://api.providusbank.com/api/v1/wallet/merchant"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .PUT(HttpRequest.BodyPublishers.ofString("{\"reference\":\"REF123456789\"}"))
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
  "reference": "REF123456789"
}";
var content = new StringContent(json, Encoding.UTF8, "application/json");
var response = await client.PUTAsync("https://api.providusbank.com/api/v1/wallet/merchant", content);

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```

