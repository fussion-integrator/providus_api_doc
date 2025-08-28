# Get All Invitations

Retrieve a paginated list of team invitations.

*   **Endpoint**: `GET {{base-url}}/team/invitations?page={page}&perPage={perPage}`
    
*   **Query Parameters**:
    
    *   `page`: Page number (e.g., `1`).
        
    *   `perPage`: Number of items per page (e.g., `20`).
        
    
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
              "id": "d3448217-ddb0-413f-a6eb-332e00bb270c",
              "email": "[email protected]",
              "role": "Secretary",
              "accepted": false,
              "createdAt": "2020-12-02T22:26:13.323Z",
              "updatedAt": "2020-12-02T22:26:13.323Z"
            }
          ]
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/team/invitations'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Team Members](/xpress-wallet-api/merchant/team/get-team-members)[NextResend Invitation](/xpress-wallet-api/merchant/team/resend-invitation)

Last updated 26 days ago