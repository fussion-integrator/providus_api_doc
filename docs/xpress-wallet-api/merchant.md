# Merchant

[Customers](/xpress-wallet-api/merchant/customers)[Wallet](/xpress-wallet-api/merchant/wallet)[Transactions](/xpress-wallet-api/merchant/transactions)[Transfer](/xpress-wallet-api/merchant/transfer)[Card](/xpress-wallet-api/merchant/card)[Team](/xpress-wallet-api/merchant/team)[Roles & Permission](/xpress-wallet-api/merchant/roles-and-permission)[Account verification](/xpress-wallet-api/merchant/account-verification)[Resend Verification Code](/xpress-wallet-api/merchant/resend-verification-code)[Complete Merchant KYC](/xpress-wallet-api/merchant/complete-merchant-kyc)[Get Merchant Profile](/xpress-wallet-api/merchant/get-merchant-profile)[Update Merchant Profile](/xpress-wallet-api/merchant/update-merchant-profile)[Get Merchant Access Keys](/xpress-wallet-api/merchant/get-merchant-access-keys)[Generate Access Keys](/xpress-wallet-api/merchant/generate-access-keys)[Switch Account Mode](/xpress-wallet-api/merchant/switch-account-mode)[Merchant Registration](/xpress-wallet-api/merchant/merchant-registration)[Get Merchant Wallet](/xpress-wallet-api/merchant/get-merchant-wallet)

## Base URL

```
https://api.providusbank.com
```

## Endpoint

<div class="method get">GET</div> `/api/v1/wallet/merchant`



## Response Body

### Success Response (200 OK)

```json
{
  "status": "success",
  "message": "Operation completed successfully",
  "data": {
    "items": [],
    "total": 0
  }
}
```

## Sample Implementation

```curl
curl -X GET "https://api.providusbank.com/api/v1/wallet/merchant" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

```python
import requests

url = "https://api.providusbank.com/api/v1/wallet/merchant"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.get(url, headers=headers)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/v1/wallet/merchant', {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
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

$context = stream_context_create([
    'http' => [
        'method' => 'GET',
        'header' => implode("\r\n", $headers)
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
    .GET(HttpRequest.BodyPublishers.noBody())
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

var response = await client.GetAsync("https://api.providusbank.com/api/v1/wallet/merchant");

var responseContent = await response.Content.ReadAsStringAsync();
Console.WriteLine(responseContent);
```