# Merchant Registration

Register a new merchant account.

*   **Endpoint**: `POST {{base-url}}/merchant`
    
*   **Body**:
    
    Copy
    
    ```
    {
      "firstName": "Yemi",
      "lastName": "Alade",
      "password": "cGFzc3dvcmQ=",
      "accountNumber": "9988776633",
      "phoneNumber": "08055484569",
      "businessName": "Yemi-Alade",
      "email": "[email protected]",
      "businessType": "FINANCIAL-SERVICES",
      "sendEmail": true
    }
    ```
    
*   **Response**:
    
    *   **201 Created**:
        
        Copy
        
        ```
        {
          "status": true,
          "requireVerification": true,
          "message": "Your activation code has been sent to your email. It expires in 24 hours"
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var request = http.Request('POST', Uri.parse('{{base-url}}/merchant'));
    request.body = '''{
      "firstName": "Demo",
      "lastName": "User",
      "password": "password",
      "businessName": "Neyosoft",
      "phoneNumber": "+2349034514808",
      "email": "[email protected]",
      "businessType": "FINANCIAL-SERVICES"
    }''';
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousSwitch Account Mode](/xpress-wallet-api/merchant/switch-account-mode)[NextGet Merchant Wallet](/xpress-wallet-api/merchant/get-merchant-wallet)

Last updated 26 days ago