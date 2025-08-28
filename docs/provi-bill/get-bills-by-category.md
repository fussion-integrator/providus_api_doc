# Get Bills by Category

**Endpoint**: `GET /bill/assigned/byCategoryId/{categoryId}`

**Description**: Retrieves a list of bills associated with a specific category ID.

**Authentication**: Basic Auth (Username, Password)

**Path Parameters**:

*   categoryId (required): The ID of the category (e.g., 4 for Electricity - Prepaid).
    

**Response**:

*   **200 OK**: Returns a JSON array of bill objects.
    

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
  --url 'http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4' \
  --header 'Authorization: Basic <base64-encoded-username:password>'
```

Copy

```
import requests

headers = {
    'Authorization': 'Basic <base64-encoded-username:password>'
}

response = requests.get('http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4', headers=headers)
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
        URL url = new URL("http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4");
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

fetch('http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4', {
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

curl_setopt($ch, CURLOPT_URL, "http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4");
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

            var response = await client.GetAsync("http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4");
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
        "bill_id": 7,
        "category_id": "4",
        "description": "Ikeja Electric - DML bill",
        "list_order": "1",
        "name": "Ikeja Electric - IKEDC",
        "source_id": ""
    },
    ...
]
```

[PreviousGet Categories](/provi-bill/get-categories)[NextGet Field](/provi-bill/get-field)

Last updated 24 days ago