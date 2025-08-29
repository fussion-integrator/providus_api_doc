# Customer to Customer Wallet Transfer

Transfer funds between customer wallets.

*   **Endpoint**: `POST {{base-url}}/transfer/wallet`
    
*   **Headers**:

    ```
    {
      "Authorization": "Bearer {{vault:authorization-secret}}",
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:

    ```
    {
      "amount": 200,
      "fromCustomerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
      "toCustomerId": "a2c40f33-489c-480f-9d24-e2742502b85f"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Transaction successfully completed.",
          "data": {
            "amount": 200,
            "reference": "ZUxe2hsW0PZWRH96u0MJrMkcwmtnLe4HczmD",
            "transaction_fee": 10,
            "total": 210,
            "target_customer_id": "a2c40f33-489c-480f-9d24-e2742502b85f",
            "source_customer_id": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
            "target_customer_wallet": "75d3cb93-eb95-4b7b-b650-b5907dce526d",
            "source_customer_wallet": "b222dee2-4e45-483c-89c7-1afe72c9bcab",
            "description": "Fund transfer between customers"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/transfer/wallet'));
    request.body = '''{
      "amount": 200,
      "fromCustomerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
      "toCustomerId": "a2c40f33-489c-480f-9d24-e2742502b85f"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousMerchant Batch Bank Transfer](/xpress-wallet-api/merchant/transfer/merchant-batch-bank-transfer)[NextCard](/xpress-wallet-api/merchant/card)