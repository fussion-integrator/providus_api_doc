# Get All Roles

Retrieve a list of all roles.

*   **Endpoint**: `GET {{base-url}}/team/roles`
    
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
          "data": [
            {
              "id": "36fb6cdc-c107-4550-9a2b-2c23ec8a78b9",
              "name": "Driver",
              "permissions": ["INVITE_TEAM_MEMBER"]
            },
            ...
          ]
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/team/roles'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet All Permissions](/xpress-wallet-api/merchant/roles-and-permission/get-all-permissions)[NextCreate Role](/xpress-wallet-api/merchant/roles-and-permission/create-role)

Last updated 26 days ago