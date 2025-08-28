# Get Merchant Access Keys

Retrieve the merchant's access keys.

*   **Endpoint**: `GET {{base-url}}/merchant/my-access-keys`
    
*   **Headers**:

    ```
    {
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
            "privateKey": "sk_sandbox_A7piqhVbmy5dzuvUQRWDIWAscnG9ZhtkmU90LdhbtR1vvi1W",
            "publicKey": "pk_sandbox_OsCl755PRpMq0tc1YxGuesXTgVBzprF2mAB8vXUuozuxyldi"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/merchant/my-access-keys'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousUpdate Merchant Profile](/xpress-wallet-api/merchant/update-merchant-profile)[NextGenerate Access Keys](/xpress-wallet-api/merchant/generate-access-keys)

Last updated 26 days ago