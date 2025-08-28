# Accept Invitation

Accept a team invitation.

*   **Endpoint**: `POST {{base-url}}/team/invitations/accept`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:
    
    Copy
    
    ```
    {
      "invitationCode": "dfnacefu;iavbklsfjakls;dfjncaksdjfakl;sdj",
      "firstName": "Emma",
      "lastName": "Adeniyi",
      "phoneNumber": "08035458867",
      "password": "cGFzc3dvcmQ="
    }
    ```
    
*   **Response**:
    
    *   **200 OK**: (Successful acceptance)
        
    *   **400 Bad Request**:
        
        Copy
        
        ```
        {
          "status": false,
          "message": "An account with the provided details already exists."
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/team/invitations/accept'));
    request.body = '''{
      "email": "[email protected]",
      "firstName": "Emma",
      "lastName": "Adeniyi",
      "phoneNumber": "08035458867",
      "password": "cGFzc3dvcmQ="
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousResend Invitation](/xpress-wallet-api/merchant/team/resend-invitation)[NextGet Merchant List](/xpress-wallet-api/merchant/team/get-merchant-list)

Last updated 26 days ago