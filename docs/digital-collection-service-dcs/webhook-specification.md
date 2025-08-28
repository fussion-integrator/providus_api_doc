# Webhook Specification

**Webhook Logic Requirements**:

1.  Validate X-Auth-Signature using SHA512(Client-Id:ClientSecret).
    
2.  Confirm settlementId and accountNumber exist and are valid.
    
3.  Return:
    
    *   "success" (code 00) if valid.
        
    *   "duplicate transaction" (code 01) if settlementId already processed.
        
    *   "rejected transaction" (code 02) if request is invalid.
        
    *   "system failure, retry" (code 03) for internal errors.
        
    

* * *

`POST` `https://api-staging.providusbank.com/v1/webhook`

Webhook Request (From DCS)

Copy

```
{
"sessionId": "000004210301180534806663649508",
  "accountNumber": "9977581536",
  "tranRemarks": "FROM UBA/...",
  "transactionAmount": "1",
  "settledAmount": "1",
  "feeAmount": "0",
  "vatAmount": "0",
  "currency": "NGN",
  "initiationTranRef": "kjhghjk",
  "settlementId": "202210301006807600001432",
  "sourceAccountNumber": "2093566866",
  "sourceAccountName": "CASAFINA CREDIT-EASY LOAN",
  "sourceBankName": "UNITED BANK FOR AFRICA",
  "channelId": "1",
  "tranDateTime": "2021-03-01 18:06:20"
}
```

**Webhook Responses**:

*   **Success**:
    

Copy

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "success",
  "responseCode": "00"
}
```

*   **Duplicate**:
    

Copy

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "duplicate transaction",
  "responseCode": "01"
}
```

*   **Rejected**:
    

Copy

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "rejected transaction",
  "responseCode": "02"
}
```

*   **System Failure**:
    

Copy

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "system failure, retry",
  "responseCode": "03"
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
curl -X POST https://your-webhook-endpoint.com/webhook \
-H "Client-Id: dGVzdF9Qcm92aWR1cw==" \
-H "X-Auth-Signature: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7" \
-H "Content-Type: application/json" \
-d '{
  "sessionId": "000004210301180534806663649508",
  "accountNumber": "9977581536",
  "tranRemarks": "FROM UBA/...",
  "transactionAmount": "1",
  "settledAmount": "1",
  "feeAmount": "0",
  "vatAmount": "0",
  "currency": "NGN",
  "initiationTranRef": "kjhghjk",
  "settlementId": "202210301006807600001432",
  "sourceAccountNumber": "2093566866",
  "sourceAccountName": "CASAFINA CREDIT-EASY LOAN",
  "sourceBankName": "UNITED BANK FOR AFRICA",
  "channelId": "1",
  "tranDateTime": "2021-03-01 18:06:20"
}'
```

Copy

```
from flask import Flask, request, jsonify
import hashlib

app = Flask(__name__)

client_id = "dGVzdF9Qcm92aWR1cw=="
client_secret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8"
expected_signature = hashlib.sha512(f"{client_id}:{client_secret}".encode()).hexdigest().upper()

@app.route('/webhook', methods=['POST'])
def webhook():
    received_signature = request.headers.get('X-Auth-Signature')
    if received_signature != expected_signature:
        return jsonify({
            "requestSuccessful": true,
            "sessionId": request.json.get('sessionId'),
            "responseMessage": "rejected transaction",
            "responseCode": "02"
        })

    data = request.json
    session_id = data.get('sessionId')
    settlement_id = data.get('settlementId')
    account_number = data.get('accountNumber')

    # Simulate database check for account and settlement ID
    if not account_number or not settlement_id:
        return jsonify({
            "requestSuccessful": true,
            "sessionId": session_id,
            "responseMessage": "rejected transaction",
            "responseCode": "02"
        })

    # Simulate check for duplicate settlement ID
    if is_duplicate_settlement(settlement_id):  # Implement your logic
        return jsonify({
            "requestSuccessful": true,
            "sessionId": session_id,
            "responseMessage": "duplicate transaction",
            "responseCode": "01"
        })

    # Simulate successful processing
    return jsonify({
        "requestSuccessful": true,
        "sessionId": session_id,
        "responseMessage": "success",
        "responseCode": "00"
    })

def is_duplicate_settlement(settlement_id):
    # Implement logic to check if settlement_id was processed
    return False  # Placeholder

if __name__ == '__main__':
    app.run(port=5000)
```

Copy

```
import com.fasterxml.jackson.databind.ObjectMapper;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestHeader;
import org.springframework.web.bind.annotation.RestController;
import javax.xml.bind.DatatypeConverter;
import java.security.MessageDigest;
import java.util.HashMap;
import java.util.Map;

@RestController
public class WebhookController {

    private final String clientId = "dGVzdF9Qcm92aWR1cw==";
    private final String clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";

    @PostMapping("/webhook")
    public ResponseEntity<Map<String, Object>> handleWebhook(
            @RequestHeader("X-Auth-Signature") String receivedSignature,
            @RequestBody Map<String, Object> payload) {
        try {
            // Generate expected signature
            MessageDigest digest = MessageDigest.getInstance("SHA-512");
            byte[] hash = digest.digest((clientId + ":" + clientSecret).getBytes("UTF-8"));
            String expectedSignature = DatatypeConverter.printHexBinary(hash).toUpperCase();

            // Initialize response map
            Map<String, Object> response = new HashMap<>();
            response.put("requestSuccessful", true);
            response.put("sessionId", payload.getOrDefault("sessionId", ""));

            // Validate signature
            if (!expectedSignature.equals(receivedSignature)) {
                response.put("responseMessage", "rejected transaction");
                response.put("responseCode", "02");
                return ResponseEntity.ok(response);
            }

            // Extract payload fields
            String sessionId = (String) payload.getOrDefault("sessionId", "");
            String settlementId = (String) payload.getOrDefault("settlementId", "");
            String accountNumber = (String) payload.getOrDefault("accountNumber", "");

            // Validate required fields
            if (accountNumber.isEmpty() || settlementId.isEmpty()) {
                response.put("responseMessage", "rejected transaction");
                response.put("responseCode", "02");
                return ResponseEntity.ok(response);
            }

            // Check for duplicate settlement ID (implement your logic)
            if (isDuplicateSettlement(settlementId)) {
                response.put("responseMessage", "duplicate transaction");
                response.put("responseCode", "01");
                return ResponseEntity.ok(response);
            }

            // Successful processing
            response.put("responseMessage", "success");
            response.put("responseCode", "00");
            return ResponseEntity.ok(response);

        } catch (Exception e) {
            // Handle internal errors
            Map<String, Object> response = new HashMap<>();
            response.put("requestSuccessful", true);
            response.put("sessionId", payload.getOrDefault("sessionId", ""));
            response.put("responseMessage", "system failure, retry");
            response.put("responseCode", "03");
            return ResponseEntity.ok(response);
        }
    }

    private boolean isDuplicateSettlement(String settlementId) {
        // Implement logic to check if settlementId was previously processed
        // Example: Query your database
        return false; // Placeholder
    }
}
```

Copy

```
const express = require('express');
const crypto = require('crypto');

const app = express();
app.use(express.json());

const clientId = 'dGVzdF9Qcm92aWR1cw==';
const clientSecret = '29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8';
const expectedSignature = crypto.createHash('sha512').update(`${clientId}:${clientSecret}`).digest('hex').toUpperCase();

app.post('/webhook', (req, res) => {
    const receivedSignature = req.headers['x-auth-signature'];
    if (receivedSignature !== expectedSignature) {
        return res.json({
            requestSuccessful: true,
            sessionId: req.body.sessionId,
            responseMessage: 'rejected transaction',
            responseCode: '02'
        });
    }

    const { sessionId, settlementId, accountNumber } = req.body;

    if (!accountNumber || !settlementId) {
        return res.json({
            requestSuccessful: true,
            sessionId,
            responseMessage: 'rejected transaction',
            responseCode: '02'
        });
    }

    if (isDuplicateSettlement(settlementId)) { // Implement your logic
        return res.json({
            requestSuccessful: true,
            sessionId,
            responseMessage: 'duplicate transaction',
            responseCode: '01'
        });
    }

    res.json({
        requestSuccessful: true,
        sessionId,
        responseMessage: 'success',
        responseCode: '00'
    });
});

function isDuplicateSettlement(settlementId) {
    // Implement logic to check if settlementId was processed
    return false; // Placeholder
}

app.listen(5000, () => console.log('Webhook server running on port 5000'));
```

Copy

```
<?php
$clientId = "dGVzdF9Qcm92aWR1cw==";
$clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";
$expectedSignature = strtoupper(hash('sha512', $clientId . ':' . $clientSecret));

header('Content-Type: application/json');

$input = file_get_contents('php://input');
$data = json_decode($input, true);
$receivedSignature = isset($_SERVER['HTTP_X_AUTH_SIGNATURE']) ? $_SERVER['HTTP_X_AUTH_SIGNATURE'] : '';

if ($receivedSignature !== $expectedSignature) {
    echo json_encode([
        'requestSuccessful' => true,
        'sessionId' => $data['sessionId'] ?? '',
        'responseMessage' => 'rejected transaction',
        'responseCode' => '02'
    ]);
    exit;
}

$sessionId = $data['sessionId'] ?? '';
$settlementId = $data['settlementId'] ?? '';
$accountNumber = $data['accountNumber'] ?? '';

if (empty($accountNumber) || empty($settlementId)) {
    echo json_encode([
        'requestSuccessful' => true,
        'sessionId' => $sessionId,
        'responseMessage' => 'rejected transaction',
        'responseCode' => '02'
    ]);
    exit;
}

if (isDuplicateSettlement($settlementId)) { // Implement your logic
    echo json_encode([
        'requestSuccessful' => true,
        'sessionId' => $sessionId,
        'responseMessage' => 'duplicate transaction',
        'responseCode' => '01'
    ]);
    exit;
}

echo json_encode([
    'requestSuccessful' => true,
    'sessionId' => $sessionId,
    'responseMessage' => 'success',
    'responseCode' => '00'
]);

function isDuplicateSettlement($settlementId) {
    // Implement logic to check if settlementId was processed
    return false; // Placeholder
}
?>
```

Copy

```
using Microsoft.AspNetCore.Mvc;
using System;
using System.IO;
using System.Security.Cryptography;
using System.Text;
using System.Threading.Tasks;

namespace WebhookController
{
    [ApiController]
    [Route("webhook")]
    public class Webhook : ControllerBase
    {
        private readonly string clientId = "dGVzdF9Qcm92aWR1cw==";
        private readonly string clientSecret = "29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8";

        [HttpPost]
        public async Task<IActionResult> Post()
        {
            using (var sha512 = SHA512.Create())
            {
                byte[] bytes = Encoding.UTF8.GetBytes(clientId + ":" + clientSecret);
                byte[] hash = sha512.ComputeHash(bytes);
                string expectedSignature = BitConverter.ToString(hash).Replace("-", "").ToUpper();

                string receivedSignature = Request.Headers["X-Auth-Signature"];
                if (receivedSignature != expectedSignature)
                {
                    return Ok(new
                    {
                        requestSuccessful = true,
                        sessionId = Request.Form["sessionId"],
                        responseMessage = "rejected transaction",
                        responseCode = "02"
                    });
                }

                using (var reader = new StreamReader(Request.Body, Encoding.UTF8))
                {
                    string body = await reader.ReadToEndAsync();
                    dynamic data = Newtonsoft.Json.JsonConvert.DeserializeObject(body);
                    string sessionId = data.sessionId;
                    string settlementId = data.settlementId;
                    string accountNumber = data.accountNumber;

                    if (string.IsNullOrEmpty(accountNumber) || string.IsNullOrEmpty(settlementId))
                    {
                        return Ok(new
                        {
                            requestSuccessful = true,
                            sessionId,
                            responseMessage = "rejected transaction",
                            responseCode = "02"
                        });
                    }

                    if (IsDuplicateSettlement(settlementId)) // Implement your logic
                    {
                        return Ok(new
                        {
                            requestSuccessful = true,
                            sessionId,
                            responseMessage = "duplicate transaction",
                            responseCode = "01"
                        });
                    }

                    return Ok(new
                    {
                        requestSuccessful = true,
                        sessionId,
                        responseMessage = "success",
                        responseCode = "00"
                    });
                }
            }
        }

        private bool IsDuplicateSettlement(string settlementId)
        {
            // Implement logic to check if settlementId was processed
            return false; // Placeholder
        }
    }
}
```

> The above command returns JSON structured like this:

Copy

```
{
  "requestSuccessful": true,
  "sessionId": "99990000554443332221",
  "responseMessage": "success",
  "responseCode": "00"
}
```

[PreviousVerify Transaction by Settlement ID](/digital-collection-service-dcs/verify-transaction-by-settlement-id)[NextTHIRD PARTY GENERIC API](/third-party-generic-api)

Last updated 1 month ago