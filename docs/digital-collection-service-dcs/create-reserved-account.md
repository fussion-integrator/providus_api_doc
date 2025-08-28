# Create Reserved Account

* * *

#### 

[](#production-base-url)

Production Base URL

http://154.113.16.142:8088/appdevapi/api/

#### 

[](#http-request)

HTTP Request

POST /PiPCreateReservedAccountNumber

* * *

POST http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber

#### 

[](#request-body)

Request Body

```
{
  "account_name": "lemuel",
  "bvn": ""
}
```

200 Success

[](#tab-id-200-success)

401: Unauthorized

[](#tab-id-401-unauthorized)

400: Bad Request .

[](#tab-id-400-bad-request)

500: Internal Server Error

[](#tab-id-500-internal-server-error)

```
{
  "account_number": "9977577067",
  "account_name": "MERCHANT(lemuel)",
  "bvn": "",
  "requestSuccessful": true,
  "responseMessage": "Reserved Account Generated Successfully",
  "responseCode": "00"
}
```

```
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}
```

```
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}
```

```
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
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
curl -X POST http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7" \
-H "Content-Type: application/json" \
-d '{"account_name":"lemuel","bvn":""}'
```

```
import requests
import hashlib

client_id = "dGVzdF9Qcm92aWR1cw=="
client_secret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8"
signature = hashlib.sha512(f"{client_id}:{client_secret}".encode()).hexdigest().upper()

url = "http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber"
headers = {
    "Client-Id": client_id,
    "X-Auth-Signature": signature,
    "Content-Type": "application/json"
}
data = {"account_name": "lemuel", "bvn": ""}
response = requests.post(url, json=data, headers=headers)
print(response.json())
```

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.security.MessageDigest;

public class CreateReservedAccount {
    public static void main(String[] args) throws Exception {
        String clientId = "dGVzdF9Qcm92aWR1cw==";
        String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        String signature = MessageDigest.getInstance("SHA-512")
            .digest((clientId + ":" + clientSecret).getBytes("UTF-8"))
            .toString().toUpperCase();

        URL url = new URL("http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Client-Id", clientId);
        conn.setRequestProperty("X-Auth-Signature", signature);
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"account_name\":\"lemuel\",\"bvn\":\"\"}";
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

> The above command returns JSON structured like this:

```
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}
```

```
const fetch = require('node-fetch');
const crypto = require('crypto');

const clientId = 'dGVzdF9Qcm92aWR1cw==';
const clientSecret = '29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8';
const signature = crypto.createHash('sha512').update(`${clientId}:${clientSecret}`).digest('hex').toUpperCase();

const url = 'http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber';
const headers = {
    'Client-Id': clientId,
    'X-Auth-Signature': signature,
    'Content-Type': 'application/json'
};
const data = { account_name: 'lemuel', bvn: '' };

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
$clientId = "dGVzdF9Qcm92aWR1cw==";
$clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
$signature = strtoupper(hash('sha512', $clientId . ':' . $clientSecret));

$url = "http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber";
$headers = [
    "Client-Id: $clientId",
    "X-Auth-Signature: $signature",
    "Content-Type: application/json"
];
$data = ["account_name" => "lemuel", "bvn" => ""];

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

> The above command returns JSON structured like this:

```
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}
```

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;
using System.Security.Cryptography;

class Program
{
    static async Task Main()
    {
        string clientId = "dGVzdF9Qcm92aWR1cw==";
        string clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        using (var sha512 = SHA512.Create())
        {
            byte[] bytes = Encoding.UTF8.GetBytes(clientId + ":" + clientSecret);
            byte[] hash = sha512.ComputeHash(bytes);
            string signature = BitConverter.ToString(hash).Replace("-", "").ToUpper();

            using (var client = new HttpClient())
            {
                client.DefaultRequestHeaders.Add("Client-Id", clientId);
                client.DefaultRequestHeaders.Add("X-Auth-Signature", signature);
                var content = new StringContent(
                    "{\"account_name\":\"lemuel\",\"bvn\":\"\"}",
                    Encoding.UTF8,
                    "application/json"
                );
                var response = await client.PostAsync("http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber", content);
                var responseString = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseString);
            }
        }
    }
}
```

The above command returns JSON structured like this:

```
{
  "account_number": "9977577067",
  "account_name": "MERCHANT(lemuel)",
  "bvn": "",
  "requestSuccessful": true,
  "responseMessage": "Reserved Account Generated Successfully",
  "responseCode": "00"
}
```

[PreviousDigital Collection Service (DCS)](/digital-collection-service-dcs)[NextCreate Dynamic Account](/digital-collection-service-dcs/create-dynamic-account)

Last updated 1 month ago