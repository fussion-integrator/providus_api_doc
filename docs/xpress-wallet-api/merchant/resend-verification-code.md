# Resend Verification Code

Resend a verification code to a merchant's email.

*   **Endpoint**: `POST {{base-url}}/merchant/verify/resend`
    
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
      "email": "[email protected]"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Your verification code has been sent to your email. It expires in 24 hours"
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/merchant/resend-activation-code'));
    request.body = '''{
      "email": "[email protected]"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousAccount verification](/xpress-wallet-api/merchant/account-verification)[NextComplete Merchant KYC](/xpress-wallet-api/merchant/complete-merchant-kyc)