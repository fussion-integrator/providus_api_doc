# Get Categories

**Endpoint**: `GET /categories`

**Description**: Retrieves a list of available bill categories.

**Authentication**: Basic Auth (Username, Password)

**Response**:

**200 OK**: Returns a JSON array of category objects.

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
curl --request GET \
  --url 'http://154.113.16.142:9999/provipay/webapi/categories' \
  --header 'Authorization: Basic <base64-encoded-username:password>'
```

Copy

```
import requests

headers = {
    'Authorization': 'Basic <base64-encoded-username:password>'
}

response = requests.get('http://154.113.16.142:9999/provipay/webapi/categories', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:9999/provipay/webapi/categories");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("Authorization", "Basic <base64-encoded-username:password>");

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

Copy

```
const headers = {
    'Authorization': 'Basic <base64-encoded-username:password>'
};

fetch('http://154.113.16.142:9999/provipay/webapi/categories', {
    method: 'GET',
    headers: headers
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

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://154.113.16.142:9999/provipay/webapi/categories");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'Authorization: Basic <base64-encoded-username:password>'
]);

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

> The above command returns JSON structured like this:

Copy

```
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}
```

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("Authorization", "Basic <base64-encoded-username:password>");

            var response = await client.GetAsync("http://154.113.16.142:9999/provipay/webapi/categories");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

**Example Response**:

Copy

```
[
    {
        "category_id": 1,
        "list_order": "1",
        "name": "Airtime TopUp"
    },
    {
        "category_id": 1007,
        "list_order": "1",
        "name": "Transportation"
    },
    ...
]
```

[PreviousProvi Bill](/provi-bill)[NextGet Bills by Category](/provi-bill/get-bills-by-category)

Last updated 24 days ago