# User

* * *

**URI**: /NIPFundTransfer

**HTTP Method**: POST

**Headers**:

*   Accept: application/json
    
*   Content-Type: application/json
    

**Request body**

Copy

```
{
  "beneficiaryAccountName": "UGBO, CHARLES UMORE",
  "transactionAmount": "2000.45",
  "currencyCode": "NGN",
  "narration": "Testing",
  "sourceAccountName": "Nnamdi Adebayo Hamzat",
  "beneficiaryAccountNumber": "0045434120",
  "beneficiaryBank": "000013",
  "transactionReference": "20191119143854",
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

Copy

```
{
  "transactionReference": "20191119143854",
  "sessionId": "999037230913163757005000082268",
  "responseMessage": "Approved or completed successfully",
  "responseCode": "00"
}
```

Copy

```
{
  "transactionReference": "20191119143501",
  "responseMessage": "TRANSACTION REFERENCE EXISTS",
  "responseCode": "7709"
}
```

Copy

```
{
  "transactionReference": "20191119143501",
  "responseMessage": "TRANSACTION REFERENCE EXISTS",
  "responseCode": "7709"
}
```

Copy

```
{
  "transactionReference": "20191119143501",
  "responseMessage": "TRANSACTION REFERENCE EXISTS",
  "responseCode": "7709"
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
curl -X POST http://154.113.16.142:8882/postingrest/NIPFundTransfer \
-H "Accept: application/json" \
-H "Content-Type: application/json" \
-d '{"beneficiaryAccountName":"UGBO, CHARLES UMORE","transactionAmount":"2000.45","currencyCode":"NGN","narration":"Testing","sourceAccountName":"Nnamdi Adebayo Hamzat","beneficiaryAccountNumber":"0045434120","beneficiaryBank":"000013","transactionReference":"20191119143854","userName":"test","password":"test"}'
```

Copy

```
import requests

url = "http://154.113.16.142:8882/postingrest/NIPFundTransfer"
headers = {"Accept": "application/json", "Content-Type": "application/json"}
data = {
    "beneficiaryAccountName": "UGBO, CHARLES UMORE",
    "transactionAmount": "2000.45",
    "currencyCode": "NGN",
    "narration": "Testing",
    "sourceAccountName": "Nnamdi Adebayo Hamzat",
    "beneficiaryAccountNumber": "0045434120",
    "beneficiaryBank": "000013",
    "transactionReference": "20191119143854",
    "userName": "test",
    "password": "test"
}
response = requests.post(url, json=data, headers=headers)
print(response.json())
```

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class NIPFundTransfer {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:8882/postingrest/NIPFundTransfer");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Accept", "application/json");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"beneficiaryAccountName\":\"UGBO, CHARLES UMORE\",\"transactionAmount\":\"2000.45\",\"currencyCode\":\"NGN\",\"narration\":\"Testing\",\"sourceAccountName\":\"Nnamdi Adebayo Hamzat\",\"beneficiaryAccountNumber\":\"0045434120\",\"beneficiaryBank\":\"000013\",\"transactionReference\":\"20191119143854\",\"userName\":\"test\",\"password\":\"test\"}";
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

Copy

```
const fetch = require('node-fetch');

const url = 'http://154.113.16.142:8882/postingrest/NIPFundTransfer';
const headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
};
const data = {
    beneficiaryAccountName: 'UGBO, CHARLES UMORE',
    transactionAmount: '2000.45',
    currencyCode: 'NGN',
    narration: 'Testing',
    sourceAccountName: 'Nnamdi Adebayo Hamzat',
    beneficiaryAccountNumber: '0045434120',
    beneficiaryBank: '000013',
    transactionReference: '20191119143854',
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

Copy

```
<?php
$url = "http://154.113.16.142:8882/postingrest/NIPFundTransfer";
$headers = [
    "Accept: application/json",
    "Content-Type: application/json"
];
$data = [
    "beneficiaryAccountName" => "UGBO, CHARLES UMORE",
    "transactionAmount" => "2000.45",
    "currencyCode" => "NGN",
    "narration" => "Testing",
    "sourceAccountName" => "Nnamdi Adebayo Hamzat",
    "beneficiaryAccountNumber" => "0045434120",
    "beneficiaryBank" => "000013",
    "transactionReference" => "20191119143854",
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

Copy

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
                "{\"beneficiaryAccountName\":\"UGBO, CHARLES UMORE\",\"transactionAmount\":\"2000.45\",\"currencyCode\":\"NGN\",\"narration\":\"Testing\",\"sourceAccountName\":\"Nnamdi Adebayo Hamzat\",\"beneficiaryAccountNumber\":\"0045434120\",\"beneficiaryBank\":\"000013\",\"transactionReference\":\"20191119143854\",\"userName\":\"test\",\"password\":\"test\"}",
                Encoding.UTF8,
                "application/json"
            );
            var response = await client.PostAsync("http://154.113.16.142:8882/postingrest/NIPFundTransfer", content);
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
  "transactionReference": "20191119143854",
  "sessionId": "999037230913163757005000082268",
  "responseMessage": "Approved or completed successfully",
  "responseCode": "00"
}
```

[PreviousRefresh Token](/xpress-wallet-api/authentication/refresh-token)[NextGet user profile](/xpress-wallet-api/user/get-user-profile)

Last updated 1 month ago