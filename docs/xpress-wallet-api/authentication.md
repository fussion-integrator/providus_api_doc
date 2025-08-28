# Authentication

Token-Based Authentication

*   **Login**: Use the /auth/login endpoint to authenticate with email and password (base64-encoded) to receive X-Access-Token and X-Refresh-Token.
    
*   **Refresh Tokens**: Use /auth/refresh/token with the X-Refresh-Token to obtain new access tokens.
    
*   **Logout**: Invalidate tokens via /auth/logout.
    
*   **Headers**:
    
    *   X-Access-Token: Required for authenticated requests.
        
    *   X-Refresh-Token: Used for token refresh.
        
    *   Example: X-Access-Token: {{access-token}}
        
    

#### 

[](#sample-login-request)

Sample Login Request

Copy

```
{
  "email": "bWVyY2hhbnQxQG1haWxpbmF0b3IuY29t",
  "password": "cGFzc3dvcmQ="
}
```

#### 

[](#sample-response)

Sample Response

Copy

```
{
  "status": true,
  "data": {
    "id": "425bc461-9b6c-4036-b47a-9d96e4f21eba",
    "role": "USER",
    "email": "[email protected]",
    "lastName": "Obagunwa",
    "firstName": "Samson",
    "createdAt": "2021-08-16T22:59:27.026Z",
    "updatedAt": "2022-05-03T11:01:11.923Z"
  },
  "merchant": {
    "email": "[email protected]",
    "id": "e84a4677-3158-40ba-8967-f523c2315cf9",
    "lastName": "Obagunwa",
    "mode": "SANDBOX",
    "role": "Admin",
    "firstName": "Samson",
    "owner": false,
    "review": "PENDING",
    "businessName": "Caleb",
    "businessType": "Restaurants",
    "createdAt": "2022-05-03T10:18:19.172Z",
    "updatedAt": "2022-05-03T10:18:19.172Z"
  }
}
```

*   Headers include X-Access-Token and X-Refresh-Token for subsequent requests.
    

### 

[](#api-endpoints)

API Endpoints

#### 

[](#authentication)

Authentication

**Login**

*   **Endpoint**: {{base-url}}/auth/login
    
*   **Method**: POST
    
*   **Description**: Authenticate a merchant and receive access and refresh tokens.
    
*   **Request Body**:
    
    Copy
    
    ```
    {
      "email": "bWVyY2hhbnQxQG1haWxpbmF0b3IuY29t",
      "password": "cGFzc3dvcmQ="
    }
    ```
    
*   **Response**: 200 OK with token headers and user/merchant data (see above).
    

**Logout**

*   **Endpoint**: {{base-url}}/auth/logout
    
*   **Method**: POST
    
*   **Description**: Invalidate the current session tokens.
    
*   **Headers**:
    
    *   X-Access-Token: {{access-token}}
        
    *   X-Refresh-Token: {{refresh-token}}
        
    
*   **Response**: 200 OK (no body).
    

**Forget Password**

*   **Endpoint**: {{base-url}}/auth/password/forget
    
*   **Method**: POST
    
*   **Description**: Request a password reset code via email.
    
*   **Request Body**:
    
    Copy
    
    ```
    {
      "email": "[email protected]"
    }
    ```
    
*   **Response**: 200 OK
    
    Copy
    
    ```
    {
      "status": true,
      "message": "Your reset code has been sent to your email. It expires in 24 hours."
    }
    ```
    

**Reset Password**

*   **Endpoint**: {{base-url}}/auth/password/reset
    
*   **Method**: POST
    
*   **Description**: Reset the password using a reset code.
    
*   **Request Body**:
    
    Copy
    
    ```
    {
      "resetCode": "3122489",
      "password": "password"
    }
    ```
    
*   **Response**: 200 OK
    
    Copy
    
    ```
    {
      "status": true,
      "message": "Password reset successfully"
    }
    ```
    

**Refresh Tokens**

*   **Endpoint**: {{base-url}}/auth/refresh/token
    
*   **Method**: POST
    
*   **Description**: Refresh access tokens using a valid refresh token.
    
*   **Headers**: X-Refresh-Token: Cx9AH9ubWqG3JyBz8DZr-E6aTa8GKruNerzJRCDUFbyjM6ef
    
*   **Response**: 200 OK with new X-Access-Token and X-Refresh-Token.
    

**HTTP Method**: POST

**Headers**:

*   Accept: application/json
    
*   Content-Type: application/json
    

**Request Parameters** (JSON):

* * *

Copy

```
{
  "accountNumber": "1018996198",
  "beneficiaryBank": "110000",
  "userName": "test",
  "password": "test"
}
```

200 Success

[](#tab-id-200-success)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request .

[](#tab-id-400-bad-request)

500: Internal Server Error

[](#tab-id-500-internal-server-error)

Copy

```
{
  "bankCode": "110000",
  "accountName": "NNAJI, JOSHUA & VIVIAN",
  "transactionReference": "",
  "bvn": "",
  "responseMessage": "Approved or completed successfully",
  "accountNumber": "1018996198",
  "responseCode": "00"
}
```

Copy

```
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}
```

Copy

```
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}
```

Copy

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

Copy

```
curl -X POST http://154.113.16.142:8882/postingrest/GetNIPAccount \
-H "Accept: application/json" \
-H "Content-Type: application/json" \
-d '{"accountNumber":"1018996198","beneficiaryBank":"110000","userName":"test","password":"test"}'
```

Copy

```
import requests

url = "http://154.113.16.142:8882/postingrest/GetNIPAccount"
headers = {"Accept": "application/json", "Content-Type": "application/json"}
data = {
    "accountNumber": "1018996198",
    "beneficiaryBank": "110000",
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

public class GetNIPAccount {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:8882/postingrest/GetNIPAccount");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Accept", "application/json");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"accountNumber\":\"1018996198\",\"beneficiaryBank\":\"110000\",\"userName\":\"test\",\"password\":\"test\"}";
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

const url = 'http://154.113.16.142:8882/postingrest/GetNIPAccount';
const headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
};
const data = {
    accountNumber: '1018996198',
    beneficiaryBank: '110000',
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
$url = "http://154.113.16.142:8882/postingrest/GetNIPAccount";
$headers = [
    "Accept: application/json",
    "Content-Type: application/json"
];
$data = [
    "accountNumber" => "1018996198",
    "beneficiaryBank" => "110000",
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
                "{\"accountNumber\":\"1018996198\",\"beneficiaryBank\":\"110000\",\"userName\":\"test\",\"password\":\"test\"}",
                Encoding.UTF8,
                "application/json"
            );
            var response = await client.PostAsync("http://154.113.16.142:8882/postingrest/GetNIPAccount", content);
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
  "bankCode": "110000",
  "accountName": "NNAJI, JOSHUA & VIVIAN",
  "transactionReference": "",
  "bvn": "",
  "responseMessage": "Approved or completed successfully",
  "accountNumber": "1018996198",
  "responseCode": "00"
}
```

[PreviousXpress Wallet API](/xpress-wallet-api)[NextLogin](/xpress-wallet-api/authentication/login)

Last updated 1 month ago