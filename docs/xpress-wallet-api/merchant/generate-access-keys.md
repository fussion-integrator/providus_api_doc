# Generate Access Keys

Generate new access keys for the merchant.

*   **Endpoint**: `POST {{base-url}}/merchant/generate-access-keys`
    
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
          "data": {
            "publicKey": "pk_sandbox_a3vSGlBiRipd0Mg6tzvSxrMlhkWyTrLCGwxfoPYEsUp9Qe69",
            "privateKey": "sk_sandbox_EZ1Ysvzeb3PxPw2SfwQis8fsAWbsAjPghMrjoff0KfMhVxF0"
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
    var request = http.Request('POST', Uri.parse('{{base-url}}/merchant/my-access-keys'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Merchant Access Keys](/xpress-wallet-api/merchant/get-merchant-access-keys)[NextSwitch Account Mode](/xpress-wallet-api/merchant/switch-account-mode)

Last updated 26 days ago