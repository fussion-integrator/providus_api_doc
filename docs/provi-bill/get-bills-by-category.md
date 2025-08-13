1. Provi Bill

# Get Bills by Category

**Endpoint**`GET /bill/assigned/byCategoryId/{categoryId}`Description: Retrieves a list of bills associated with a specific category ID.

**Description**Authentication: Basic Auth (Username, Password)

**Authentication**Path Parameters:

**Path Parameters**- categoryId (required): The ID of the category (e.g., 4 for Electricity - Prepaid).

categoryId (required): The ID of the category (e.g., 4 for Electricity - Prepaid).

Response:

**Response**- 200 OK: Returns a JSON array of bill objects.

200 OK: Returns a JSON array of bill objects.

**200 OK**### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --request GET \
  --url 'http://154.113.16.142:9999/provipay/webapi/bill/assigned/byCategoryId/4' \
  --header 'Authorization: Basic <base64-encoded-username:password>'


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


Example Response:

**Example Response**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

Last updated 9 days ago