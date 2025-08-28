# Get bank account details

Verify bank account details using sort code and account number.

*   **Endpoint**: `GET {{base-url}}/transfer/account/details?sortCode={sortCode}&accountNumber={accountNumber}`
    
*   **Query Parameters**:
    
    *   `sortCode`: Bank sort code (e.g., `000023`).
        
    *   `accountNumber`: Bank account number (e.g., `1700263070`).
        
    
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
          "account": {
            "bankCode": "000013",
            "accountName": "NNAJI, JOSHUA & VIVIAN",
            "accountNumber": "0167421242"
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
    var request = http.Request('GET', Uri.parse('{{base-url}}/transfer/account/details?sortCode=000013&accountNumber=0167421242'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet bank list](/xpress-wallet-api/merchant/transfer/get-bank-list)[NextMerchant bank transfer](/xpress-wallet-api/merchant/transfer/merchant-bank-transfer)

Last updated 26 days ago