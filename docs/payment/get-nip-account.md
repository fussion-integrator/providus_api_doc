# Get NIP Account

Validate and retrieve account details for NIP transfer.

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method post">POST</div> `/api/v1/payment/nip/account`



## Request Body

```json
{
  "accountNumber": "1234567890",
  "bankCode": "044"
}
```




## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "data": {
    "accountName": "John Doe",
    "accountNumber": "1234567890"
  }
}
```


## Sample Implementation

```curl
curl -X POST "https://api.providusbank.com/api/v1/payment/nip/account" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "accountNumber": "1234567890",
  "bankCode": "044"
}'
```

```python
import requests

url = "https://api.providusbank.com/api/v1/payment/nip/account"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

data = {
  "accountNumber": "1234567890",
  "bankCode": "044"
}
response = requests.post(url, headers=headers, json=data)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/payment/nip/account', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
  "accountNumber": "1234567890",
  "bankCode": "044"
})
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "https://api.providusbank.com/api/v1/payment/nip/account";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$data = json_encode({
  \"accountNumber\": \"1234567890\",
  \"bankCode\": \"044\"
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
    .uri(URI.create("https://api.providusbank.com/api/v1/payment/nip/account"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .POST(HttpRequest.BodyPublishers.ofString("{\"accountNumber\":\"1234567890\",\"bankCode\":\"044\"}"))
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
  "accountNumber": "1234567890",
  "bankCode": "044"
}";
var content = new StringContent(json, Encoding.UTF8, "application/json");
var response = await client.PostAsync("https://api.providusbank.com/api/v1/payment/nip/account", content);

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```

