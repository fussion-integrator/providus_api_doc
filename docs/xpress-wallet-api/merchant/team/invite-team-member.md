# Invite Team Member

Send an invitation to a new team member.

*   **Endpoint**: `POST {{base-url}}/team/invitations`
    
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
      "roleId": "1e9f0636-1e3c-409a-a8bd-3b037410530f",
      "email": "[email protected]",
      "approvalLimit": 0
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Invitation successfully sent."
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/team/invitations'));
    request.body = '''{
      "role": "Secretary",
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
    

[PreviousTeam](/xpress-wallet-api/merchant/team)[NextGet Team Members](/xpress-wallet-api/merchant/team/get-team-members)

Last updated 26 days ago