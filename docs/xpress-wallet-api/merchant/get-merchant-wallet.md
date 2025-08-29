# Get Merchant Wallet

Retrieve the merchant's wallet details.

*   **Endpoint**: `GET {{base-url}}/merchant/wallet`
    
*   **Headers**:

    ```
    {
      "Authorization": "Bearer {{vault:authorization-secret}}",
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "data": {
            "id": "cbaade0f-c413-479c-b405-e40406c70a80",
            "email": "[email protected]",
            "bankName": "Providus Bank",
            "bankCode": "101",
            "accountName": "Samsung Limited",
            "businessName": "Samsung Limited",
            "accountNumber": "8857460982",
            "bookedBalance": 0,
            "availableBalance": 0,
            "accountReference": "gscbOelLaMy41ogFDgjgern3C7LKHnnS87TO",
            "createdAt": "2021-08-16T22:59:27.074Z",
            "updatedAt": "2021-08-16T22:59:27.074Z"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/merchant/wallet'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

* * *

[PreviousMerchant Registration](/xpress-wallet-api/merchant/merchant-registration)[NextCode Samples](/xpress-wallet-api/code-samples)