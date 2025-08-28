# Account verification

Verify a merchant account using an activation code.

*   **Endpoint**: `PUT {{base-url}}/merchant/verify`
    
*   **Body**:

    ```
    {
      "activationCode": "9004546"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Your account has been successfully verified."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var request = http.Request('PUT', Uri.parse('{{base-url}}/merchant/verify'));
    request.body = '''{
      "activationCode": "5581413"
    }''';
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousUpdate Role](/xpress-wallet-api/merchant/roles-and-permission/update-role)[NextResend Verification Code](/xpress-wallet-api/merchant/resend-verification-code)

Last updated 26 days ago