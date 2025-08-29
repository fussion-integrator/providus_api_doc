# NIP Fund Transfer

Transfer funds to other banks using the Nigeria Inter-Bank Settlement System (NIBSS) Instant Payment (NIP).

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method post">POST</div> `/api/v1/payment/nip/transfer`

## Request Body

```json
{
  "amount": 1000,
  "destinationAccountNumber": "1234567890",
  "destinationBankCode": "044",
  "narration": "Payment for services",
  "reference": "TXN123456789"
}
```


## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "data": {
    "transactionId": "TXN123456789",
    "reference": "TXN123456789",
    "amount": 1000,
    "status": "successful",
    "sessionId": "SESSION123"
  }
}
```


## Sample Implementation

```curl
curl -X POST "https://api.providusbank.com/api/v1/payment/nip/transfer" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "amount": 1000,
  "destinationAccountNumber": "1234567890",
  "destinationBankCode": "044",
  "narration": "Payment for services",
  "reference": "TXN123456789"
}'
```

```python
import requests

url = "https://api.providusbank.com/api/v1/payment/nip/transfer"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

data = {
  "amount": 1000,
  "destinationAccountNumber": "1234567890",
  "destinationBankCode": "044",
  "narration": "Payment for services",
  "reference": "TXN123456789"
}
response = requests.post(url, headers=headers, json=data)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/payment/nip/transfer', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
  "amount": 1000,
  "destinationAccountNumber": "1234567890",
  "destinationBankCode": "044",
  "narration": "Payment for services",
  "reference": "TXN123456789"
})
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "https://api.providusbank.com/api/v1/payment/nip/transfer";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$data = json_encode({
  \"amount\": 1000,
  \"destinationAccountNumber\": \"1234567890\",
  \"destinationBankCode\": \"044\",
  \"narration\": \"Payment for services\",
  \"reference\": \"TXN123456789\"
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
    .uri(URI.create("https://api.providusbank.com/api/v1/payment/nip/transfer"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .POST(HttpRequest.BodyPublishers.ofString("{\"amount\":1000,\"destinationAccountNumber\":\"1234567890\",\"destinationBankCode\":\"044\",\"narration\":\"Payment for services\",\"reference\":\"TXN123456789\"}"))
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
  "destinationAccountNumber": "1234567890",
  "destinationBankCode": "044",
  "narration": "Payment for services",
  "reference": "TXN123456789"
}";
var content = new StringContent(json, Encoding.UTF8, "application/json");
var response = await client.PostAsync("https://api.providusbank.com/api/v1/payment/nip/transfer", content);

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```

