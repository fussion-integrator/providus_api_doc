# NIPFundTransferMultipleDebitAccounts

* * *

**URI**: /NIPFundTransferMultipleDebitAccounts

**HTTP Method**: POST

**Headers**:

*   Accept: application/json
    
*   Content-Type: application/json
    

**Request body** (JSON)

* * *

```
{
  "beneficiaryAccountName": "Nathan Agbara",
  "transactionAmount": "50",
  "currencyCode": "NGN",
  "narration": "Testing",
  "debitAccount": "5900235871",
  "sourceAccountName": "NATHAN AGBARA",
  "beneficiaryAccountNumber": "0430294874",
  "beneficiaryBank": "000013",
  "transactionReference": "SDFGHJUKJ456UKJH34565",
  "userName": "test",
  "password": "test"
}
```

Response body (JSON)

200 Account successfully retrieved

[](#tab-id-200-account-successfully-retrieved)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request The server cannot process the request due to a client error, such as malformed syntax or invalid parameters in the request.

[](#tab-id-400-bad-request-the-server-cannot-process-the-request-due-to-a-client-error-such-as-malformed-syntax)

500: Internal Server Error Server encountered an unexpected error

[](#tab-id-500-internal-server-error-server-encountered-an-unexpected-error)

```
{
  "transactionReference": "35326323fghn",
  "responseMessage": "Approved or completed successfully",
  "responseCode": "00"
}
```

```
{
  "responseMessage": "Account does not exist.",
  "responseCode": "01"
}
```

```
{
  "responseMessage": "Account does not exist.",
  "responseCode": "01"
}
```

```
{
  "responseMessage": "Account does not exist.",
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
curl -X POST http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts \
-H "Accept: application/json" \
-H "Content-Type: application/json" \
-d '{"beneficiaryAccountName":"Nathan Agbara","transactionAmount":"50","currencyCode":"NGN","narration":"Testing","debitAccount":"5900235871","sourceAccountName":"NATHAN AGBARA","beneficiaryAccountNumber":"0430294874","beneficiaryBank":"000013","transactionReference":"SDFGHJUKJ456UKJH34565","userName":"test","password":"test"}'
```

```
import requests

url = "http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts"
headers = {"Accept": "application/json", "Content-Type": "application/json"}
data = {
    "beneficiaryAccountName": "Nathan Agbara",
    "transactionAmount": "50",
    "currencyCode": "NGN",
    "narration": "Testing",
    "debitAccount": "5900235871",
    "sourceAccountName": "NATHAN AGBARA",
    "beneficiaryAccountNumber": "0430294874",
    "beneficiaryBank": "000013",
    "transactionReference": "SDFGHJUKJ456UKJH34565",
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

public class NIPFundTransferMultipleDebitAccounts {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Accept", "application/json");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"beneficiaryAccountName\":\"Nathan Agbara\",\"transactionAmount\":\"50\",\"currencyCode\":\"NGN\",\"narration\":\"Testing\",\"debitAccount\":\"5900235871\",\"sourceAccountName\":\"NATHAN AGBARA\",\"beneficiaryAccountNumber\":\"0430294874\",\"beneficiaryBank\":\"000013\",\"transactionReference\":\"SDFGHJUKJ456UKJH34565\",\"userName\":\"test\",\"password\":\"test\"}";
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

const url = 'http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts';
const headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
};
const data = {
    beneficiaryAccountName: 'Nathan Agbara',
    transactionAmount: '50',
    currencyCode: 'NGN',
    narration: 'Testing',
    debitAccount: '5900235871',
    sourceAccountName: 'NATHAN AGBARA',
    beneficiaryAccountNumber: '0430294874',
    beneficiaryBank: '000013',
    transactionReference: 'SDFGHJUKJ456UKJH34565',
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
$url = "http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts";
$headers = [
    "Accept: application/json",
    "Content-Type: application/json"
];
$data = [
    "beneficiaryAccountName" => "Nathan Agbara",
    "transactionAmount" => "50",
    "currencyCode" => "NGN",
    "narration" => "Testing",
    "debitAccount" => "5900235871",
    "sourceAccountName" => "NATHAN AGBARA",
    "beneficiaryAccountNumber" => "0430294874",
    "beneficiaryBank" => "000013",
    "transactionReference" => "SDFGHJUKJ456UKJH34565",
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
                "{\"beneficiaryAccountName\":\"Nathan Agbara\",\"transactionAmount\":\"50\",\"currencyCode\":\"NGN\",\"narration\":\"Testing\",\"debitAccount\":\"5900235871\",\"sourceAccountName\":\"NATHAN AGBARA\",\"beneficiaryAccountNumber\":\"0430294874\",\"beneficiaryBank\":\"000013\",\"transactionReference\":\"SDFGHJUKJ456UKJH34565\",\"userName\":\"test\",\"password\":\"test\"}",
                Encoding.UTF8,
                "application/json"
            );
            var response = await client.PostAsync("http://154.113.16.142:8882/postingrest/NIPFundTransferMultipleDebitAccounts", content);
            var responseString = await response.Content.ReadAsStringAsync();
            Console.WriteLine(responseString);
        }
    }
}
```

> The above command returns JSON structured like this:

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "success",
  "responseCode": "00"
}
```

[PreviousGetProvidusAccount](/third-party-generic-api/getprovidusaccount)[NextXpress Wallet API](/xpress-wallet-api)