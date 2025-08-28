# Get Merchant List

Retrieve a list of merchants associated with the team.

*   **Endpoint**: `GET {{base-url}}/team/merchants`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "data": [
            {
              "id": "151b73ed-93b8-4ed8-9288-6e290c2af38e",
              "role": "Secretary",
              "name": "Neyosoft"
            }
          ]
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/team/merchants'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousAccept Invitation](/xpress-wallet-api/merchant/team/accept-invitation)[NextSwitch Merchant](/xpress-wallet-api/merchant/team/switch-merchant)

Last updated 26 days ago