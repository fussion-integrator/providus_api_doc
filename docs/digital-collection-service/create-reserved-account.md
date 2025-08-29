1. Digital Collection Service (DCS)

# Create Reserved Account

Reserved accounts are static accounts assigned to a specific user. They do not expire, but should be used judiciously, as there is a limit to the number of virtual accounts that can be created.

#### Production Base URL

http://154.113.16.142:8088/appdevapi/api/

#### HTTP Request

POST /PiPCreateReservedAccountNumber

POST http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber

#### Request Body

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_name": "lemuel",
  "bvn": ""
}

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "requestSuccessful": false,
  "responseMessage": "Error Completing Operation",
  "responseCode": "11"
}
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -X POST http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7" \
-H "Content-Type: application/json" \
-d '{"account_name":"lemuel","bvn":""}'

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.security.MessageDigest;

public class CreateReservedAccount {
    public static void main(String[] args) throws Exception {
        String clientId = "dGVzdF9Qcm92aWR1cw==";
        String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
        String signature = MessageDigest.getInstance("SHA-512")
            .digest((clientId + ":" + clientSecret).getBytes("UTF-8"))
            .toString().toUpperCase();

        URL url = new URL("http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("Client-Id", clientId);
        conn.setRequestProperty("X-Auth-Signature", signature);
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInput = "{\"account_name\":\"lemuel\",\"bvn\":\"\"}";
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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
$clientId = "dGVzdF9Qcm92aWR1cw==";
$clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
$signature = strtoupper(hash('sha512', $clientId . ':' . $clientSecret));

$url = "http://154.113.16.142:8088/appdevapi/api/PiPCreateReservedAccountNumber";
$headers = [
    "Client-Id: $clientId",
    "X-Auth-Signature: $signature",
    "Content-Type: application/json"
];
$data = ["account_name" => "lemuel", "bvn" => ""];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
echo $response;
?>
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_number": "9977577067",
  "account_name": "MERCHANT(lemuel)",
  "bvn": "",
  "requestSuccessful": true,
  "responseMessage": "Reserved Account Generated Successfully",
  "responseCode": "00"
}
```