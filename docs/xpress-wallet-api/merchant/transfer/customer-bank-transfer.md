# Customer Bank Transfer

Initiate a bank transfer from a customer account.

*   **Endpoint**: `POST {{base-url}}/transfer/bank/customer`
    
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
      "amount": 150,
      "sortCode": "110005",
      "narration": "Just kidding",
      "accountNumber": "5400403011",
      "accountName": "Obagunwa Emmanuel",
      "customerId": "66f5a260-9462-4d36-ade1-beccd57e52bd",
      "metadata": {"customer-data": "some customer details"}
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Transaction successfully completed.",
          "transfer": {
            "amount": 1,
            "charges": 10.5,
            "vat": 0.7875,
            "reference": "AFYF1zFVJgwtV5YQ1wMjH7tmaQnNz6S8BqAQ",
            "total": 12.2875,
            "metadata": {"customer-data": "some customer details"},
            "sessionId": "694183772508885572057985059318",
            "destination": "0167421242/000013",
            "transactionReference": "9533043993045314",
            "description": "Transfer of NGN 1 to Obagunwa Emmanuel (0167421242/GTBANK PLC)"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/transfer/bank/customer'));
    request.body = '''{
      "amount": 1,
      "sortCode": "000013",
      "narration": "Just kidding",
      "accountNumber": "0167421242",
      "accountName": "Obagunwa Emmanuel",
      "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
      "metadata": {"customer-data": "some customer details"}
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousMerchant bank transfer](/xpress-wallet-api/merchant/transfer/merchant-bank-transfer)[NextMerchant Batch Bank Transfer](/xpress-wallet-api/merchant/transfer/merchant-batch-bank-transfer)