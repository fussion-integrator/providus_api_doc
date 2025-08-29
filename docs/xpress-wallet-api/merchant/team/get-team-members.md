# Get Team Members

Retrieve a list of team members.

*   **Endpoint**: `GET {{base-url}}/team/members`
    
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
              "id": "0b9bce55-fb6a-4249-a08b-5fb6802febac",
              "role": "Customer Representative",
              "email": "[email protected]",
              "lastName": "Doe",
              "firstName": "John",
              "approvalLimit": 0
            },
            {
              "id": "8e51036e-d88c-424c-83f1-0e2c9e2d415f",
              "role": "Customer Representative",
              "email": "[email protected]",
              "lastName": "Adeniyi",
              "firstName": "Emma",
              "approvalLimit": 0
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
    var request = http.Request('GET', Uri.parse('{{base-url}}/team/members'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

#### 

[](#undefined)

[PreviousInvite Team Member](/xpress-wallet-api/merchant/team/invite-team-member)[NextGet All Invitations](/xpress-wallet-api/merchant/team/get-all-invitations)