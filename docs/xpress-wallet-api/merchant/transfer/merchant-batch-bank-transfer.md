# Merchant Batch Bank Transfer

Initiate multiple bank transfers in a single batch.

*   **Endpoint**: `POST {{base-url}}/transfer/bank/batch`
    
*   **Headers**:

    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:

    ```
    [
      {
        "amount": 600,
        "sortCode": "000013",
        "narration": "Just kidding",
        "accountNumber": "0167421242",
        "accountName": "Obagunwa Emmanuel",
        "metadata": {"customer-data": "some customer details"}
      },
      {
        "amount": 300,
        "sortCode": "000013",
        "narration": "Just kidding",
        "accountNumber": "0167421242",
        "accountName": "Obagunwa Emmanuel",
        "metadata": {"customer-data": "some customer details"}
      }
    ]
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Transaction has been submitted."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/transfer/bank/batch'));
    request.body = '''[
      {
        "amount": 5000,
        "sortCode": "000013",
        "narration": "Just kidding",
        "accountNumber": "0167421242",
        "accountName": "Obagunwa Emmanuel",
        "metadata": {"customer-data": "some customer details"}
      },
      {
        "amount": 300,
        "sortCode": "000013",
        "narration": "Just kidding",
        "accountNumber": "0167421242",
        "accountName": "Obagunwa Emmanuel",
        "metadata": {"customer-data": "some customer details"}
      }
    ]''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousCustomer Bank Transfer](/xpress-wallet-api/merchant/transfer/customer-bank-transfer)[NextCustomer to Customer Wallet Transfer](/xpress-wallet-api/merchant/transfer/customer-to-customer-wallet-transfer)