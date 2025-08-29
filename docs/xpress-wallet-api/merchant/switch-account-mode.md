# Switch Account Mode

Switch the merchant's account mode between SANDBOX and PRODUCTION.

*   **Endpoint**: `POST {{base-url}}/merchant/account-mode`
    
*   **Headers**:

    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:

    ```
    {
      "mode": "PRODUCTION"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**: (Successful switch)
        
    *   **400 Bad Request**:

        ```
        {
          "status": false,
          "message": "Kindly complete your account verification/setup before switching account mode."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/merchant/account-mode'));
    request.body = '''{
      "mode": "SANDBOX"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGenerate Access Keys](/xpress-wallet-api/merchant/generate-access-keys)[NextMerchant Registration](/xpress-wallet-api/merchant/merchant-registration)