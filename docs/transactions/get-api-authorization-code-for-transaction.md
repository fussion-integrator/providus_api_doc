1. Transactions

# Get API authorization code for transaction

## Request Body

```json
{
  "redirect_uri": "\"redirect_uri_value\""
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|--------------|
| redirect_uri | string | The OAuth client redirect URI ( must be URL encoded ) |

Get an authorization code for the Transaction API.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

`GET /transaction/oauth/authorize/`## Authorization Code.

`GET``https://api-staging.providusbank.com/v1 /account/NIP`Get API authorization code for transaction.

#### Headers

Content-Type

String

Request content type ( application/x-www-form-urlencoded )

#### Request Body

response_type*

String

`code`client_id

String

The OAuth client id



### Sample Implementation

### Curl

```curl
curl -X POST "https://api.providusbank.com/transaction/oauth/authorize/'" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

### Python

```python
import requests

url = "https://api.providusbank.com/transaction/oauth/authorize/'"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.post(url, headers=headers)
print(response.json())
```

### Javascript

```javascript
const response = await fetch('https://api.providusbank.com/transaction/oauth/authorize/'', {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
});

const data = await response.json();
console.log(data);
```

### Nodejs

```nodejs
const axios = require('axios');

const config = {
  method: 'post',
  url: 'https://api.providusbank.com/transaction/oauth/authorize/'',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios(config)
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```

### Php

```php
<?php
$url = "https://api.providusbank.com/transaction/oauth/authorize/'";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$context = stream_context_create([
    'http' => [
        'method' => 'POST',
        'header' => implode("\r\n", $headers)
    ]
]);

$response = file_get_contents($url, false, $context);
echo $response;
?>
```

### Java

```java
import java.net.http.*;
import java.net.URI;
import java.time.Duration;

public class ApiClient {
    public static void main(String[] args) throws Exception {
        HttpClient client = HttpClient.newBuilder()
            .connectTimeout(Duration.ofSeconds(10))
            .build();
            
        HttpRequest request = HttpRequest.newBuilder()
            .uri(URI.create("https://api.providusbank.com/transaction/oauth/authorize/'"))
            .header("Authorization", "Bearer YOUR_API_KEY")
            .header("Content-Type", "application/json")
            .POST(HttpRequest.BodyPublishers.noBody())
            .build();

        HttpResponse<String> response = client.send(request, 
            HttpResponse.BodyHandlers.ofString());
        System.out.println(response.body());
    }
}
```

### Csharp

```csharp
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    private static readonly HttpClient client = new HttpClient();
    
    static async Task Main()
    {
        client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_API_KEY");
        
        var response = await client.GetAsync("https://api.providusbank.com/transaction/oauth/authorize/'");
        
        var responseContent = await response.Content.ReadAsStringAsync();
        Console.WriteLine(responseContent);
    }
}
```

### Dart

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> makeApiCall() async {
  final url = Uri.parse('https://api.providusbank.com/transaction/oauth/authorize/'');
  final headers = {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json',
  };
  
  final response = await http.post(url, headers: headers);
  
  if (response.statusCode == 200) {
    final data = jsonDecode(response.body);
    print(data);
  } else {
    print('Error: ${response.statusCode}');
  }
}
```

### Go

```go
package main

import (
    "bytes"
    "encoding/json"
    "fmt"
    "io"
    "net/http"
)

func main() {
    url := "https://api.providusbank.com/transaction/oauth/authorize/'"
    
    req, _ := http.NewRequest("POST", url, nil)
    
    req.Header.Set("Authorization", "Bearer YOUR_API_KEY")
    req.Header.Set("Content-Type", "application/json")
    
    client := &http.Client{}
    resp, err := client.Do(req)
    if err != nil {
        panic(err)
    }
    defer resp.Body.Close()
    
    body, _ := io.ReadAll(resp.Body)
    fmt.Println(string(body))
}
```

### Ruby

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.providusbank.com/transaction/oauth/authorize/'')
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request['Authorization'] = 'Bearer YOUR_API_KEY'
request['Content-Type'] = 'application/json'



response = http.request(request)
puts JSON.parse(response.body)
```

