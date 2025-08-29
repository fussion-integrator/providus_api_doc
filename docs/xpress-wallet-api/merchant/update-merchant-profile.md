# Update Merchant Profile

Update the merchant's profile information.

*   **Endpoint**: `PATCH {{base-url}}/merchant/profile`
    
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
      "canLogin": true,
      "sendEmail": true,
      "callbackURL": "http://localhost:50004/webhook/wallet",
      "sandboxCallbackURL": "https://webhook.site/7e4f1819-7780-416d-8596-3dece233d785"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Profiile successfully updated"
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('PATCH', Uri.parse('{{base-url}}/merchant/profile'));
    request.body = '''{
      "lastName": "Michael"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Merchant Profile](/xpress-wallet-api/merchant/get-merchant-profile)[NextGet Merchant Access Keys](/xpress-wallet-api/merchant/get-merchant-access-keys)