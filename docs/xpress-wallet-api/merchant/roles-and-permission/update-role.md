# Update Role

Update an existing role's name and permissions.

*   **Endpoint**: `PATCH {{base-url}}/team/roles/{roleId}`
    
*   **Path Parameters**:
    
    *   `roleId`: The unique ID of the role (e.g., `36fb6cdc-c107-4550-9a2b-2c23ec8a78b9`).
        
    
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
      "name": "Driver",
      "permissions": ["INVITE_TEAM_MEMBER", "TRANSFER_TO_BANK"]
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Role successfully updated.",
          "data": {
            "id": "36fb6cdc-c107-4550-9a2b-2c23ec8a78b9",
            "name": "Driver",
            "permissions": ["INVITE_TEAM_MEMBER", "TRANSFER_TO_BANK"]
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
    var request = http.Request('PATCH', Uri.parse('{{base-url}}/team/roles/36fb6cdc-c107-4550-9a2b-2c23ec8a78b9'));
    request.body = '''{
      "name": "Driver",
      "permissions": ["INVITE_TEAM_MEMBER", "TRANSFER_TO_BANK"]
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousCreate Role](/xpress-wallet-api/merchant/roles-and-permission/create-role)[NextAccount verification](/xpress-wallet-api/merchant/account-verification)

Last updated 26 days ago