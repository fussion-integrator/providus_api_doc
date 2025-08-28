# Verify Transaction by Settlement ID

* * *

#### 

[](#http-request)

HTTP Request

GET /PiPverifyTransaction\_sessionid?session\_id={sessionId}

* * *

Sample Url

`https://api-staging.providusbank.com/v1/PiPverifyTransaction_sessionid?session_id={sessionId}`

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
  "sessionId": "09FG240119090404935XTTGA9",
  "initiationTranRef": "",
  "accountNumber": "9977904966",
  "tranRemarks": "FROM 701/null/AT124_TRF|2MPT1xc5r|1748255361543127040/09FG240119090404935XTTGA9",
  "transactionAmount": 1000.0,
  "settledAmount": 955.0,
  "feeAmount": 45.0,
  "vatAmount": 0.0,
  "currency": "NGN",
  "settlementId": "210240119000176500002",
  "sourceAccountNumber": " ",
  "sourceAccountName": "null",
  "sourceBankCode": "701",
  "sourceBankName": "",
  "channelId": "1",
  "tranDateTime": "2024-01-19 09:04:37",
  "settlementDateTime": "1/19/2024 10:12:53 AM",
  "stamp_duty_flg": 0,
  "post_flg": 0,
  "notification_acknowledgement": 1
}
```

```
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

```
{
  "sessionId": "",
  "initiationTranRef": "",
  "accountNumber": "",
  "tranRemarks": "Transaction not found!!!",
  "transactionAmount": 0.0,
  "settledAmount": 0.0,
  "feeAmount": 0.0,
  "vatAmount": 0.0,
  "currency": "",
  "settlementId": "",
  "sourceAccountNumber": "",
  "sourceAccountName": "",
  "sourceBankCode": "",
  "sourceBankName": "",
  "channelId": "",
  "tranDateTime": "",
  "settlementDateTime": "",
  "stamp_duty_flg": 0,
  "post_flg": 0,
  "notification_acknowledgement": 0
}
```

```
{
  "sessionId": "",
  "initiationTranRef": "",
  "accountNumber": "",
  "tranRemarks": "Transaction not found!!!",
  "transactionAmount": 0.0,
  "settledAmount": 0.0,
  "feeAmount": 0.0,
  "vatAmount": 0.0,
  "currency": "",
  "settlementId": "",
  "sourceAccountNumber": "",
  "sourceAccountName": "",
  "sourceBankCode": "",
  "sourceBankName": "",
  "channelId": "",
  "tranDateTime": "",
  "settlementDateTime": "",
  "stamp_duty_flg": 0,
  "post_flg": 0,
  "notification_acknowledgement": 0
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
curl -X GET "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002" \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7"
```

```
import requests
import hashlib

client_id = "dGVzdF9Qcm92aWR1cw=="
client_secret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8"
signature = hashlib.sha512(f"{client_id}:{client_secret}".encode()).hexdigest().upper()

url = "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002"
headers = {
    "Client-Id": client_id,
    "X-Auth-Signature": signature
}
response = requests.get(url, headers=headers)
print(response.json())
```

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.security.MessageDigest;

public class VerifyTransactionSettlementId {
    public static void main(String[] args) throws Exception {
        String clientId = "dGVzdF9Qcm92aWR1cw==";
        String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        MessageDigest digest = MessageDigest.getInstance("SHA-512");
        byte[] hash = digest.digest((clientId + ":" + clientSecret).getBytes("UTF-8"));
        StringBuilder signature = new StringBuilder();
        for (byte b : hash) {
            signature.append(String.format("%02X", b));
        }

        URL url = new URL("http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("Client-Id", clientId);
        conn.setRequestProperty("X-Auth-Signature", signature.toString());

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
const crypto = require('crypto');

const clientId = 'dGVzdF9Qcm92aWR1cw==';
const clientSecret = '29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8';
const signature = crypto.createHash('sha512').update(`${clientId}:${clientSecret}`).digest('hex').toUpperCase();

const url = 'http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002';
const headers = {
    'Client-Id': clientId,
    'X-Auth-Signature': signature
};

fetch(url, {
    method: 'GET',
    headers: headers
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

$url = "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002";
$headers = [
    "Client-Id: $clientId",
    "X-Auth-Signature: $signature"
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
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
                var response = await client.GetAsync("http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_settlementid?settlement_id=210240119000176500002");
                var responseString = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseString);
            }
        }
    }
}
```

> The above command returns JSON structured like this:

```
{
  "sessionId": "09FG240119090404935XTTGA9",
  "initiationTranRef": "",
  "accountNumber": "9977904966",
  "tranRemarks": "FROM 701/null/AT124_TRF|2MPT1xc5r|1748255361543127040/09FG240119090404935XTTGA9",
  "transactionAmount": 1000.0,
  "settledAmount": 955.0,
  "feeAmount": 45.0,
  "vatAmount": 0.0,
  "currency": "NGN",
  "settlementId": "210240119000176500002",
  "sourceAccountNumber": " ",
  "sourceAccountName": "null",
  "sourceBankCode": "701",
  "sourceBankName": "",
  "channelId": "1",
  "tranDateTime": "2024-01-19 09:04:37",
  "settlementDateTime": "1/19/2024 10:12:53 AM",
  "stamp_duty_flg": 0,
  "post_flg": 0,
  "notification_acknowledgement": 1
}
```

[PreviousVerify Transaction by Session ID](/digital-collection-service-dcs/verify-transaction-by-session-id)[NextWebhook Specification](/digital-collection-service-dcs/webhook-specification)

Last updated 1 month ago