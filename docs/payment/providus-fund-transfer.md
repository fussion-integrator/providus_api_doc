# Providus Fund Transfer

Transfer funds within Providus Bank accounts.

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method post">POST</div> `/api/v1/payment/transfer`



## Request Body

```json
{
  "amount": 1000,
  "destinationAccount": "1234567890",
  "narration": "Transfer"
}
```


## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "message": "Operation completed successfully",
  "data": {
    "transactionId": "TXN123456789",
    "status": "successful"
  }
}
```

## Sample Implementation

```curl
curl -X POST "https://api.providusbank.com/api/v1/payment/transfer" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "amount": 1000,
  "destinationAccount": "1234567890",
  "narration": "Transfer"
}'
```

```python
import requests

url = "https://api.providusbank.com/api/v1/payment/transfer"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

data = {
  "amount": 1000,
  "destinationAccount": "1234567890",
  "narration": "Transfer"
}
response = requests.post(url, headers=headers, json=data)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/payment/transfer', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
  "amount": 1000,
  "destinationAccount": "1234567890",
  "narration": "Transfer"
})
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "https://api.providusbank.com/api/v1/payment/transfer";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$data = json_encode({
  \"amount\": 1000,
  \"destinationAccount\": \"1234567890\",
  \"narration\": \"Transfer\"
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
    .uri(URI.create("https://api.providusbank.com/api/v1/payment/transfer"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .POST(HttpRequest.BodyPublishers.ofString("{\"amount\":1000,\"destinationAccount\":\"1234567890\",\"narration\":\"Transfer\"}"))
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
  "amount": 1000,
  "destinationAccount": "1234567890",
  "narration": "Transfer"
}";
var content = new StringContent(json, Encoding.UTF8, "application/json");
var response = await client.PostAsync("https://api.providusbank.com/api/v1/payment/transfer", content);

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```

