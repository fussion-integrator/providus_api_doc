1. Provi Bill

# Payment

**Endpoint**`POST /makepayment`Description: Initiates a payment for a specific bill.

**Description**Authentication: Basic Auth (Username, Password)

**Authentication**Request Body (JSON):

**Request Body**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --request POST \
  --url 'http://154.113.16.142:9999/provipay/webapi/makepayment' \
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


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("http://154.113.16.142:9999/provipay/webapi/makepayment");
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


```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "http://154.113.16.142:9999/provipay/webapi/makepayment");
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


Response:

**Response**- 200 OK: Returns a JSON object with validation results.

200 OK: Returns a JSON object with validation results.

**200 OK**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "data": "{\"units\":\"85.33\",\"unitsType\":\"kWh\",\"token\":\"95015032359018227792\"}",
    "message": "Request successful",
    "responseCode": "00",
    "responseMessage": "Transaction successful"
}
```

Last updated 8 days ago