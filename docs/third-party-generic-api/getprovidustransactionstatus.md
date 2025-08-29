# GetProvidusTransactionStatus

* * *

**URI**: /GetProvidusTransactionStatus

**HTTP Method**: POST

**Headers**:

*   Accept: application/json
    
*   Content-Type: application/json
    

**Request body** (JSON):

```
{
  "transactionReference": "2345677777",
  "userName": "test",
  "password": "test"
}
```

200 Successful

[](#tab-id-200-successful)

401: Unauthorized

[](#tab-id-401-unauthorized)

400: Bad Request

[](#tab-id-400-bad-request)

500: Internal Server Error

[](#tab-id-500-internal-server-error)

```
{
  "amount": "100.0",
  "creditAccount": "1700263070",
  "debitAccount": "5900085856",
  "transactionReference": "2345677777",
  "transactionDateTime": "2020-05-04 14:12:11.0",
  "currency": "NGN",
  "responseMessage": "OPERATION SUCCESSFUL",
  "responseCode": "00"
}
```

```
{
  "responseMessage": "Transaction does not exist.",
  "responseCode": "01"
}
```

```
{
  "responseMessage": "Transaction does not exist.",
  "responseCode": "01"
}
```

```
{
  "responseMessage": "Transaction does not exist.",
  "responseCode": "01"
}
```

* * *

### 

[](#sample-implementation)

Sample Implementation

Curl

[](#tab-curl)

Python

[](#tab-python)

Java

[](#tab-java)

JavaScript

[](#tab-javascript)

PHP

[](#tab-php)

C#

[](#tab-c)

```
curl -X POST http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus \
-H "Accept: application/json" \
-H "Content-Type: application/json" \
-d '{"transactionReference":"2345677777","userName":"test","password":"test"}'
```

```
import requests

url = "http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus"
headers = {"Accept": "application/json", "Content-Type": "application/json"}
data = {
    "transactionReference": "2345677777",
    "userName": "test",
    "password": "test"
}
response = requests.post(url, json=data, headers=headers)
print(response.json())
```

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class GetProvidusTransactionStatus {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Accept", "application/json");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"transactionReference\":\"2345677777\",\"userName\":\"test\",\"password\":\"test\"}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInput.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        BufferedReader br = new BufferedReader(new InputStreamReader(conn.getInputStream(), "utf-8"));
        StringBuilder response = new StringBuilder();
        String responseLine;
        while ((responseLine = br.readLine()) != null) {
            response.append(responseLine.trim());
        }
        System.out.println(response.toString());
    }
}
```

```
const fetch = require('node-fetch');

const url = 'http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus';
const headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
};
const data = {
    transactionReference: '2345677777',
    userName: 'test',
    password: 'test'
};

fetch(url, {
    method: 'POST',
    headers: headers,
    body: JSON.stringify(data)
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

```
<?php
$url = "http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus";
$headers = [
    "Accept: application/json",
    "Content-Type: application/json"
];
$data = [
    "transactionReference" => "2345677777",
    "userName" => "test",
    "password" => "test"
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
echo $response;
?>
```

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("Accept", "application/json");
            var content = new StringContent(
                "{\"transactionReference\":\"2345677777\",\"userName\":\"test\",\"password\":\"test\"}",
                Encoding.UTF8,
                "application/json"
            );
            var response = await client.PostAsync("http://154.113.16.142:8882/postingrest/GetProvidusTransactionStatus", content);
            var responseString = await response.Content.ReadAsStringAsync();
            Console.WriteLine(responseString);
        }
    }
}
```

> The above command returns JSON structured like this:

```
{
  "amount": "100.0",
  "creditAccount": "1700263070",
  "debitAccount": "5900085856",
  "transactionReference": "2345677777",
  "transactionDateTime": "2020-05-04 14:12:11.0",
  "currency": "NGN",
  "responseMessage": "OPERATION SUCCESSFUL",
  "responseCode": "00"
}
```

[PreviousProvidusFundTransfer](/third-party-generic-api/providusfundtransfer)[NextGetProvidusAccount](/third-party-generic-api/getprovidusaccount)