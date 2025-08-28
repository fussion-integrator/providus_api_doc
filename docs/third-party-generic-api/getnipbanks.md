# GetNIPBanks

* * *

**URI**: /GetNIPBanks

**HTTP Method**: GET

**Headers**:

*   Accept: application/json
    
*   Content-Type: application/json
    

**Response:**

200 Successful

[](#tab-id-200-successful)

401: Unauthorized

[](#tab-id-401-unauthorized)

400: Bad Request

[](#tab-id-400-bad-request)

500: Internal Server Error

[](#tab-id-500-internal-server-error)

Copy

```
{
  "banks": [
    {"bankCode": "090270", "bankName": "AB MICROFINANCE BANK"},
    {"bankCode": "070010", "bankName": "ABBEY MORTGAGE BANK"},
    {"bankCode": "090260", "bankName": "ABOVE ONLY MICROFINANCE BANK"},
    {"bankCode": "090197", "bankName": "ABU MICROFINANCE BANK"},
    {"bankCode": "000014", "bankName": "ACCESS BANK"},
    {"bankCode": "100013", "bankName": "ACCESS MOBILE"},
    {"bankCode": "000005", "bankName": "ACCESS(DIAMOND) BANK"},
    {"bankCode": "090134", "bankName": "ACCION MICROFINANCE BANK"},
    ...
  ],
  "responseMessage": "SUCCESS",
  "responseCode": "00"
}
```

Copy

```
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

Copy

```
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

Copy

```
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
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

Copy

```
curl -X GET http://154.113.16.142:8882/postingrest/GetNIPBanks \
-H "Accept: application/json" \
-H "Content-Type: application/json"
```

Copy

```
import requests

url = "http://154.113.16.142:8882/postingrest/GetNIPBanks"
headers = {"Accept": "application/json", "Content-Type": "application/json"}
response = requests.get(url, headers=headers)
print(response.json())
```

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class GetNIPBanks {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:8882/postingrest/GetNIPBanks");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("Accept", "application/json");
        conn.setRequestProperty("Content-Type", "application/json");

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

Copy

```
const fetch = require('node-fetch');

const url = 'http://154.113.16.142:8882/postingrest/GetNIPBanks';
const headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
};

fetch(url, {
    method: 'GET',
    headers: headers
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));
```

Copy

```
<?php
$url = "http://154.113.16.142:8882/postingrest/GetNIPBanks";
$headers = [
    "Accept: application/json",
    "Content-Type: application/json"
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
echo $response;
?>
```

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("Accept", "application/json");
            var response = await client.GetAsync("http://154.113.16.142:8882/postingrest/GetNIPBanks");
            var responseString = await response.Content.ReadAsStringAsync();
            Console.WriteLine(responseString);
        }
    }
}
```

> The above command returns JSON structured like this:

Copy

```
{
  "banks": [
    {"bankCode": "090270", "bankName": "AB MICROFINANCE BANK"},
    {"bankCode": "070010", "bankName": "ABBEY MORTGAGE BANK"},
    {"bankCode": "090260", "bankName": "ABOVE ONLY MICROFINANCE BANK"},
    {"bankCode": "090197", "bankName": "ABU MICROFINANCE BANK"},
    {"bankCode": "000014", "bankName": "ACCESS BANK"},
    {"bankCode": "100013", "bankName": "ACCESS MOBILE"},
    {"bankCode": "000005", "bankName": "ACCESS(DIAMOND) BANK"},
    {"bankCode": "090134", "bankName": "ACCION MICROFINANCE BANK"},
    ...
  ],
  "responseMessage": "SUCCESS",
  "responseCode": "00"
}
```

[PreviousGetNIPTransactionStatus](/third-party-generic-api/getniptransactionstatus)[NextProvidusFundTransfer](/third-party-generic-api/providusfundtransfer)

Last updated 1 month ago