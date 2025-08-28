# Create Role

Create a new role with specified permissions.

*   **Endpoint**: `POST {{base-url}}/team/roles`
    
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
      "name": "Customer Representative",
      "permissions": ["BROWSE_CUSTOMERS", "UPDATE_CUSTOMERS", "CREATE_CUSTOMER_WALLET"]
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Role successfully created.",
          "data": {
            "id": "36fb6cdc-c107-4550-9a2b-2c23ec8a78b9",
            "name": "Driver",
            "permissions": ["INVITE_TEAM_MEMBER"]
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/team/roles'));
    request.body = '''{
      "name": "Driver",
      "permissions": ["INVITE_TEAM_MEMBER"]
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet All Roles](/xpress-wallet-api/merchant/roles-and-permission/get-all-roles)[NextUpdate Role](/xpress-wallet-api/merchant/roles-and-permission/update-role)

Last updated 26 days ago