# Validate

**Endpoint**: `POST /validate/{billId}/customer`

**Description**: Validates customer details for a specific bill ID before making a payment.

**Authentication**: Basic Auth (Username, Password)

**Path Parameters**:

*   billId (required): The ID of the bill (e.g., 1099).
    

**Request Body** (JSON):

```
{
    "inputs": [
        {
            "value": "2",
            "key": "merchantFK"
        },
        {
            "value": "1",
            "key": "accountType"
        },
        {
            "value": "1234567",
            "key": "customerId"
        },
        {
            "value": "dot",
            "key": "customerName"
        },
        {
            "value": "100",
            "key": "amount"
        }
    ],
    "billId": "1099",
    "customerAccountNo": "1700415109",
    "channel_ref": "122433"
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
curl --request POST \
  --url 'http://154.113.16.142:9999/provipay/webapi/validate/1099/customer' \
  --header 'Authorization: Basic <base64-encoded-username:password>' \
  --header 'Content-Type: application/json' \
  --data '{
    "inputs": [
        {
            "value": "2",
            "key": "merchantFK"
        },
        {
            "value": "1",
            "key": "accountType"
        },
        {
            "value": "1234567",
            "key": "customerId"
        },
        {
            "value": "dot",
            "key": "customerName"
        },
        {
            "value": "100",
            "key": "amount"
        }
    ],
    "billId": "1099",
    "customerAccountNo": "1700415109",
    "channel_ref": "122433"
}'
```

```
import requests

headers = {
    'Authorization': 'Basic <base64-encoded-username:password>',
    'Content-Type': 'application/json'
}

data = {
    "inputs": [
        {"value": "2", "key": "merchantFK"},
        {"value": "1", "key": "accountType"},
        {"value": "1234567", "key": "customerId"},
        {"value": "dot", "key": "customerName"},
        {"value": "100", "key": "amount"}
    ],
    "billId": "1099",
    "customerAccountNo": "1700415109",
    "channel_ref": "122433"
}

response = requests.post('http://154.113.16.142:9999/provipay/webapi/validate/1099/customer', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:9999/provipay/webapi/validate/1099/customer");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Authorization", "Basic <base64-encoded-username:password>");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"inputs\": [{\"value\": \"2\", \"key\": \"merchantFK\"}, {\"value\": \"1\", \"key\": \"accountType\"}, {\"value\": \"1234567\", \"key\": \"customerId\"}, {\"value\": \"dot\", \"key\": \"customerName\"}, {\"value\": \"100\", \"key\": \"amount\"}], \"billId\": \"1099\", \"customerAccountNo\": \"1700415109\", \"channel_ref\": \"122433\"}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

```
const headers = {
    'Authorization': 'Basic <base64-encoded-username:password>',
    'Content-Type': 'application/json'
};

fetch('http://154.113.16.142:9999/provipay/webapi/validate/1099/customer', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        inputs: [
            { value: "2", key: "merchantFK" },
            { value: "1", key: "accountType" },
            { value: "1234567", key: "customerId" },
            { value: "dot", key: "customerName" },
            { value: "100", key: "amount" }
        ],
        billId: "1099",
        customerAccountNo: "1700415109",
        channel_ref: "122433"
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://154.113.16.142:9999/provipay/webapi/validate/1099/customer");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'Authorization: Basic <base64-encoded-username:password>',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"inputs": [{"value": "2", "key": "merchantFK"}, {"value": "1", "key": "accountType"}, {"value": "1234567", "key": "customerId"}, {"value": "dot", "key": "customerName"}, {"value": "100", "key": "amount"}], "billId": "1099", "customerAccountNo": "1700415109", "channel_ref": "122433"}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("Authorization", "Basic <base64-encoded-username:password>");

            var content = new StringContent(
                "{\"inputs\": [{\"value\": \"2\", \"key\": \"merchantFK\"}, {\"value\": \"1\", \"key\": \"accountType\"}, {\"value\": \"1234567\", \"key\": \"customerId\"}, {\"value\": \"dot\", \"key\": \"customerName\"}, {\"value\": \"100\", \"key\": \"amount\"}], \"billId\": \"1099\", \"customerAccountNo\": \"1700415109\", \"channel_ref\": \"122433\"}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("http://154.113.16.142:9999/provipay/webapi/validate/1099/customer", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

**Response**:

*   **200 OK**: Returns a JSON object with validation results.

```
{
    "balance": "",
    "customer_name": "NP NGEMA",
    "message": "Request successful",
    "successful": true
}
```

[PreviousGet Field](/provi-bill/get-field)[NextPayment](/provi-bill/payment)

Last updated 24 days ago