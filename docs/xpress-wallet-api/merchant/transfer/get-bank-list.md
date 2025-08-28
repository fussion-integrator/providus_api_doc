# Get bank list

Retrieve a list of supported banks.

*   **Endpoint**: `GET {{base-url}}/transfer/banks`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "banks": [
            {"code": "090270", "name": "AB MICROFINANCE BANK"},
            {"code": "000014", "name": "ACCESS BANK"},
            {"code": "000013", "name": "GTBANK PLC"},
            ...
          ]
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/transfer/banks'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousTransfer](/xpress-wallet-api/merchant/transfer)[NextGet bank account details](/xpress-wallet-api/merchant/transfer/get-bank-account-details)

Last updated 26 days ago