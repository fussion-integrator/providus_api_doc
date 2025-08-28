# Update Member Information

Update a team member's information.

*   **Endpoint**: `PUT {{base-url}}/team/member/{memberId}`
    
*   **Path Parameters**:
    
    *   `memberId`: The unique ID of the team member (e.g., `0b9bce55-fb6a-4249-a08b-5fb6802febac`).
        
    
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
      "approvalLimit": 500,
      "roleId": "477cd8ea-55c4-4a3a-ab24-d3e7bbcb283c"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Member information successfully updated."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('PUT', Uri.parse('{{base-url}}/team/member/0b9bce55-fb6a-4249-a08b-5fb6802febac'));
    request.body = '''{
      "approvalLimit": 500
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousSwitch Merchant](/xpress-wallet-api/merchant/team/switch-merchant)[NextRoles & Permission](/xpress-wallet-api/merchant/roles-and-permission)

Last updated 26 days ago