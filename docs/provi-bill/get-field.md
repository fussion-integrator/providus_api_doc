1. Provi Bill

# Get Field

**Endpoint**`GET /field/assigned/byBillId/{billId}`Description: Retrieves the fields required for a specific bill ID.

**Description**Authentication: Basic Auth (Username, Password)

**Authentication**Path Parameters:

**Path Parameters**- billId (required): The ID of the bill (e.g., 1099 for Ikeja Prepaid).

billId (required): The ID of the bill (e.g., 1099 for Ikeja Prepaid).

Response:

**Response**- 200 OK: Returns a JSON object containing the bill ID, fee, field ID, fields, type, and validation status.

200 OK: Returns a JSON object containing the bill ID, fee, field ID, fields, type, and validation status.

**200 OK**### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --request GET \
  --url 'http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099' \
  --header 'Authorization: Basic <base64-encoded-username:password>'
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests

headers = {
    'Authorization': 'Basic <base64-encoded-username:password>'
}

response = requests.get('http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099");
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
const headers = {
    'Authorization': 'Basic <base64-encoded-username:password>'
};

fetch('http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099', {
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099");
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

            var response = await client.GetAsync("http://154.113.16.142:9999/provipay/webapi/field/assigned/byBillId/1099");
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

Example Response:

**Example Response**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bill_id": 1099,
    "fee": 0,
    "field_id": 1093,
    "fields": [
        {
            "call_tag": "",
            "field_type": "compulsory",
            "key": "merchantFK",
            "list": {
                "items": [
                    {
                        "id": "2",
                        "name": "Ikeja Electricity Prepaid"
                    }
                ],
                "list_type": "single"
            },
            "name": "Biller Name"
        },
        ...
    ],
    "type": "static",
    "validate": "y"
}
```

Last updated 8 days ago