# Resend Invitation

Resend an invitation to a team member.

*   **Endpoint**: `POST {{base-url}}/team/invitations/resend`
    
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
      "email": "[email protected]"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Invitation successfully resend."
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/team/invitations/resend'));
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
    

[PreviousGet All Invitations](/xpress-wallet-api/merchant/team/get-all-invitations)[NextAccept Invitation](/xpress-wallet-api/merchant/team/accept-invitation)

Last updated 26 days ago