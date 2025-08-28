# Merchant bank transfer

Initiate a bank transfer from a merchant account.

*   **Endpoint**: `POST {{base-url}}/transfer/bank`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "Authorization": "Bearer {{vault:authorization-secret}}",
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:
    
    Copy
    
    ```
    {
      "amount": 220,
      "sortCode": "000023",
      "narration": "Just kidding",
      "accountNumber": "1700263070",
      "accountName": "Obagunwa Emmanuel",
      "metadata": {"customer-data": "some customer details"}
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Transaction successfully completed.",
          "transfer": {
            "amount": 100,
            "charges": 10.5,
            "vat": 0.7875,
            "reference": "Lf9PAUXREbIyUM2tKU1nGJP2W3vxpLV5s18R",
            "total": 111.2875,
            "metadata": {"customer-data": "some customer details"},
            "sessionId": "965755343713226737061061390325",
            "destination": "0167421242/000013",
            "transactionReference": "0496626196169490",
            "description": "Transfer of NGN 100 to Obagunwa Emmanuel (0167421242/GTBANK PLC)"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/transfer/bank'));
    request.body = '''{
      "amount": 100,
      "sortCode": "000013",
      "narration": "Just kidding",
      "accountNumber": "0167421242",
      "accountName": "Obagunwa Emmanuel",
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
    

[PreviousGet bank account details](/xpress-wallet-api/merchant/transfer/get-bank-account-details)[NextCustomer Bank Transfer](/xpress-wallet-api/merchant/transfer/customer-bank-transfer)

Last updated 26 days ago