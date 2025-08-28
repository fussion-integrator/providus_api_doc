1. Provi Bill

# Get Categories

**Endpoint**`GET /categories`Description: Retrieves a list of available bill categories.

**Description**Authentication: Basic Auth (Username, Password)

**Authentication**Response:

**Response**200 OK: Returns a JSON array of category objects.

**200 OK**### Sample Implementation

```curl
curl -X GET "https://api.providusbank.com/api/endpoint" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

```python
import requests

url = "https://api.providusbank.com/api/endpoint"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.get(url, headers=headers)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/endpoint', {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
});

const data = await response.json();
console.log(data);
```

```nodejs
const axios = require('axios');

const config = {
  method: 'get',
  url: 'https://api.providusbank.com/api/endpoint',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
};

axios(config)
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```

```php
<?php
$url = "https://api.providusbank.com/api/endpoint";
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
import java.time.Duration;

public class ApiClient {
    public static void main(String[] args) throws Exception {
        HttpClient client = HttpClient.newBuilder()
            .connectTimeout(Duration.ofSeconds(10))
            .build();
            
        HttpRequest request = HttpRequest.newBuilder()
            .uri(URI.create("https://api.providusbank.com/api/endpoint"))
            .header("Authorization", "Bearer YOUR_API_KEY")
            .header("Content-Type", "application/json")
            .GET(HttpRequest.BodyPublishers.noBody())
            .build();

        HttpResponse<String> response = client.send(request, 
            HttpResponse.BodyHandlers.ofString());
        System.out.println(response.body());
    }
}
```

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
        
        var response = await client.GetAsync("https://api.providusbank.com/api/endpoint");
        
        var responseContent = await response.Content.ReadAsStringAsync();
        Console.WriteLine(responseContent);
    }
}
```

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<void> makeApiCall() async {
  final url = Uri.parse('https://api.providusbank.com/api/endpoint');
  final headers = {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json',
  };
  
  final response = await http.get(url, headers: headers);
  
  if (response.statusCode == 200) {
    final data = jsonDecode(response.body);
    print(data);
  } else {
    print('Error: ${response.statusCode}');
  }
}
```

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
    url := "https://api.providusbank.com/api/endpoint"
    
    req, _ := http.NewRequest("GET", url, nil)
    
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

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.providusbank.com/api/endpoint')
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Get.new(uri)
request['Authorization'] = 'Bearer YOUR_API_KEY'
request['Content-Type'] = 'application/json'



response = http.request(request)
puts JSON.parse(response.body)
```

