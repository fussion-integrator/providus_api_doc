1. Digital Collection Service (DCS)

# Blacklist/Whitelist Account

Blacklist accounts suspected of fraudulent activity to prevent funds from reaching your settlement account. Blacklisted accounts can receive funds, but notifications are not processed until whitelistd

The /PiPBlacklistAccount endpoint is used when you suspect that a user is using an account for fraudulent transactions. To prevent funds transferred to such an account from eventually entering your settlement account, you can call this endpoint to blacklist the account.

*The /PiPBlacklistAccount endpoint is used when you suspect that a user is using an account for fraudulent transactions. To prevent funds transferred to such an account from eventually entering your settlement account, you can call this endpoint to blacklist the account.*Please note that virtual accounts cannot be deleted—they can only be blacklisted using the /PiPBlacklistAccount endpoint. Also, blacklisted accounts can still receive funds; however, payment notifications will not be processed successfully until the blacklist flag is removed.

*Please note that virtual accounts cannot be deleted—they can only be blacklisted using the /PiPBlacklistAccount endpoint. Also, blacklisted accounts can still receive funds; however, payment notifications will not be processed successfully until the blacklist flag is removed.*To remove a blacklist (i.e., to whitelist an account), use the /PiPBlacklistAccount endpoint with the appropriate flag.

*To remove a blacklist (i.e., to whitelist an account), use the /PiPBlacklistAccount endpoint with the appropriate flag.*#### Production Base URL

http://154.113.16.142:8088/appdevapi/api/

#### HTTP Request

POST /PiPBlacklistAccount

`https://api-staging.providusbank.com/v1/PiPBlacklistAccount`To Blacklist an account, set the blacklist_flag to 1, set to 0 if you want to whitelist the account

Request (Blacklist)

**Request (Blacklist)**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_number": "9977708171",
  "blacklist_flg": 1
}
```

Request (Whitelist)

**Request (Whitelist)**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_number": "9977708171",
  "blacklist_flg": 0
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": true,
  "responseMessage": "account blacklisted / whitelisted successfully",
  "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": false,
  "responseMessage": "Exception; Failed",
  "responseCode": "03"
}
```

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -X POST http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7" \
-H "Content-Type: application/json" \
-d '{"account_number":"9977708171","blacklist_flg":1}'
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
import hashlib

client_id = "dGVzdF9Qcm92aWR1cw=="
client_secret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8"
signature = hashlib.sha512(f"{client_id}:{client_secret}".encode()).hexdigest().upper()

url = "http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount"
headers = {
    "Client-Id": client_id,
    "X-Auth-Signature": signature,
    "Content-Type": "application/json"
}
data = {"account_number": "9977708171", "blacklist_flg": 1}
response = requests.post(url, json=data, headers=headers)
print(response.json())
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.security.MessageDigest;

public class BlacklistAccount {
    public static void main(String[] args) throws Exception {
        String clientId = "dGVzdF9Qcm92aWR1cw==";
        String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        String signature = MessageDigest.getInstance("SHA-512")
            .digest((clientId + ":" + clientSecret).getBytes("UTF-8"))
            .toString().toUpperCase();

        URL url = new URL("http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Client-Id", clientId);
        conn.setRequestProperty("X-Auth-Signature", signature);
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"account_number\":\"9977708171\",\"blacklist_flg\":1}";
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
const fetch = require('node-fetch');
const crypto = require('crypto');

const clientId = 'dGVzdF9Qcm92aWR1cw==';
const clientSecret = '29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8';
const signature = crypto.createHash('sha512').update(`${clientId}:${clientSecret}`).digest('hex').toUpperCase();

const url = 'http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount';
const headers = {
    'Client-Id': clientId,
    'X-Auth-Signature': signature,
    'Content-Type': 'application/json'
};
const data = { account_number: '9977708171', blacklist_flg: 1 };

fetch(url, {
    method: 'POST',
    headers: headers,
    body: JSON.stringify(data)
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

$url = "http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount";
$headers = [
    "Client-Id: $clientId",
    "X-Auth-Signature: $signature",
    "Content-Type: application/json"
];
$data = ["account_number" => "9977708171", "blacklist_flg" => 1];

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
                var content = new StringContent(
                    "{\"account_number\":\"9977708171\",\"blacklist_flg\":1}",
                    Encoding.UTF8,
                    "application/json"
                );
                var response = await client.PostAsync("http://154.113.16.142:8088/appdevapi/api/PiPBlacklistAccount", content);
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
  "requestSuccessful": true,
  "responseMessage": "OPERATION SUCCESSFUL",
  "responseCode": "00"
}
```

Last updated 23 days ago