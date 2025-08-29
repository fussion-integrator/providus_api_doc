# Get All Permissions

Retrieve a list of all available permissions.

*   **Endpoint**: `GET {{base-url}}/team/permissions`
    
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
            {"name": "BROWSE_CUSTOMERS", "description": "View customers information"},
            {"name": "UPDATE_CUSTOMERS", "description": "Update customers information"},
            {"name": "CREATE_CUSTOMER_WALLET", "description": "Create wallet for customers"},
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
    var request = http.Request('GET', Uri.parse('{{base-url}}/team/permissions'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousRoles & Permission](/xpress-wallet-api/merchant/roles-and-permission)[NextGet All Roles](/xpress-wallet-api/merchant/roles-and-permission/get-all-roles)