1. Digital Collection Service (DCS)

# Create Dynamic Account

Dynamic accounts are for one-time payments and can be reassigned. They expire 10 minutes after creation by default (extendable up to 48 hours).

Dynamic accounts are designed for one-time payments and can be assigned to different users. By default, they expire 10 minutes after creation (this can be extended up to a maximum of 48 hours) before being reassigned to another user. They must be used for a single payment before expiration.

*Dynamic accounts are designed for one-time payments and can be assigned to different users. By default, they expire 10 minutes after creation (this can be extended up to a maximum of 48 hours) before being reassigned to another user. They must be used for a single payment before expiration.*#### Production Base URL

http://154.113.16.142:8088/appdevapi/api/

#### HTTP Request

POST /PiPCreateDynamicAccountNumber

Post http://154.113.16.142:8088/appdevapi/api/PiPCreateDnamicAccountNumber

Request (Auto-gen Reference)

**Request (Auto-gen Reference)**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_name": "lemuel"
}


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_number": "9978012701",
  "account_name": "lemuel",
  "requestSuccessful": true,
  "responseMessage": "OPERATION SUCCESSFUL",
  "responseCode": "00",
  "initiationTranRef": "Prov2312"
}


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
"requestSuccessful": false,
"responseMessage": "Error Completing Operation",
"responseCode": "03",
"initiationTranRef": ""
}


### Sample Implementation

```curl
curl -X POST "https://api.providusbank.com/api/endpoint" \
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

response = requests.post(url, headers=headers)
print(response.json())
```

```javascript
const response = await fetch('https://api.providusbank.com/api/endpoint', {
  method: 'POST',
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
  method: 'post',
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
        'method' => 'POST',
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
            .POST(HttpRequest.BodyPublishers.noBody())
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
  
  final response = await http.post(url, headers: headers);
  
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

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.providusbank.com/api/endpoint')
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request['Authorization'] = 'Bearer YOUR_API_KEY'
request['Content-Type'] = 'application/json'



response = http.request(request)
puts JSON.parse(response.body)
```

