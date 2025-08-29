1. Digital Collection Service (DCS)

# Verify Transaction by Session ID

Verify transactions using the session ID provided in webhook notifications to confirm they originate from Providus Bank.

#### HTTP Request

GET /PiPverifyTransaction_sessionid?session_id={sessionId}

`PiPverifyTransaction_sessionid?session_id={sessionId}````inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -X GET "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9" \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7"
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
import hashlib

client_id = "dGVzdF9Qcm92aWR1cw=="
client_secret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8"
signature = hashlib.sha512(f"{client_id}:{client_secret}".encode()).hexdigest().upper()

url = "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9"
headers = {
    "Client-Id": client_id,
    "X-Auth-Signature": signature
}
response = requests.get(url, headers=headers)
print(response.json())
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.security.MessageDigest;

public class VerifyTransactionSessionId {
    public static void main(String[] args) throws Exception {
        String clientId = "dGVzdF9Qcm92aWR1cw==";
        String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        MessageDigest digest = MessageDigest.getInstance("SHA-512");
        byte[] hash = digest.digest((clientId + ":" + clientSecret).getBytes("UTF-8"));
        StringBuilder signature = new StringBuilder();
        for (byte b : hash) {
            signature.append(String.format("%02X", b));
        }

        URL url = new URL("http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9");
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
const fetch = require('node-fetch');
const crypto = require('crypto');

const clientId = 'dGVzdF9Qcm92aWR1cw==';
const clientSecret = '29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8';
const signature = crypto.createHash('sha512').update(`${clientId}:${clientSecret}`).digest('hex').toUpperCase();

const url = 'http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9';
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
$clientId = "dGVzdF9Qcm92aWR1cw==";
$clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
$signature = strtoupper(hash('sha512', $clientId . ':' . $clientSecret));

$url = "http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9";
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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
                var response = await client.GetAsync("http://154.113.16.142:8088/appdevapi/api/PiPverifyTransaction_sessionid?session_id=09FG240119090404935XTTGA9");
                var responseString = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseString);
            }
        }
    }
}
```

> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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